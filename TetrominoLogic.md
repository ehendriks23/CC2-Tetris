```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TetrominoLogic : MonoBehaviour
{
    GameSpace gameSpace;
    float timer = 0f;
    bool movable = true;
    public GameObject rig;

    // Start is called before the first frame update
    void Start()
    {
        gameSpace = FindObjectOfType<GameSpace>();
    }
    
    //Registers the final position of a Tetronimo, this allows for block collision.
    void RegisterTetromino()
    {
        foreach (Transform subTetromino in rig.transform)
        {
            gameSpace.grid[Mathf.FloorToInt(subTetromino.position.x), Mathf.FloorToInt(subTetromino.position.y)] = subTetromino;
        }
    }

    //CheckValid() checks whether or not a Tetromino block can actually make that move. Checks validity of move.
    //Determines validity based on x and y coordinate thresholds.
    bool CheckValid()
    {
        foreach (Transform subTetromino in rig.transform)
        {
            if (subTetromino.transform.position.x >= GameSpace.width ||
                subTetromino.transform.position.x < 0 ||
                subTetromino.transform.position.y < 0)
            {
                return false;
            }

            if (gameSpace.grid[Mathf.FloorToInt(subTetromino.position.x), Mathf.FloorToInt(subTetromino.position.y)] != null)
            {
                return false;
                //states that if it runs into a registered Tetromino, it won't move and will spawn a new Tetromino
            }
        }
        return true;
    }
    
    // Update is called once per frame
    void Update()
    {
        if (movable)
        {
            //Timer
            timer += 1 * Time.deltaTime;

            //Manually Dropping
            if (Input.GetKeyDown(KeyCode.DownArrow) && timer > GameSpace.quickDropTime)
            {
                gameObject.transform.position -= new Vector3(0, 1, 0);
                timer = 0;
                //States that if the move is not valid, the Tetromino's position will get reverted.
                if(!CheckValid())
                {
                    movable = false;
                    gameObject.transform.position += new Vector3(0, 1, 0);
                    RegisterTetromino();
                    gameSpace.ClearLines();
                    gameSpace.SpawnTetromino();
                }
            }
            //Naturally falling blocks
            else if (timer > GameSpace.dropTime)
            {
                gameObject.transform.position -= new Vector3(0, 1, 0);
                timer = 0;
                if (!CheckValid())
                {
                    movable = false;
                    gameObject.transform.position += new Vector3(0, 1, 0);
                    RegisterTetromino();
                    gameSpace.SpawnTetromino();
                }
            }

            //Moving Left and Right.
            if (Input.GetKeyDown(KeyCode.LeftArrow))
            {
                gameObject.transform.position -= new Vector3(1, 0, 0);
                if (!CheckValid())
                {
                    gameObject.transform.position += new Vector3(1, 0, 0);
                }

            }

            if (Input.GetKeyDown(KeyCode.RightArrow))
            {
                gameObject.transform.position += new Vector3(1, 0, 0);
                if(!CheckValid())
                {
                    gameObject.transform.position -= new Vector3(1, 0, 0);
                }
            }

            //Rotating Tetrominos
            if (Input.GetKeyDown(KeyCode.Space))
            {
                rig.transform.eulerAngles += new Vector3(0, 0, 90);
                if(!CheckValid())
                {
                    movable = false;
                    rig.transform.eulerAngles -= new Vector3(0, 0, 90);
                }
            }
        }
    }
}

