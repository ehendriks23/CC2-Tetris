using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class GameSpace : MonoBehaviour
{
    //Tetromino Falling
    public static float dropTime = 0.9f;
    public static float quickDropTime = 0.05f;
    public static int width = 17, height = 29;
    public GameObject[] tetrominos;
    public Transform[,] grid = new Transform[width, height];

    // Start is called before the first frame update
    void Start()
    {
        SpawnTetromino();
    }

    public void ClearLines()
    {
        for (int y = 0; y < height; y++)
        {
            if (CompleteLine(y))
            {
                DestroyLine(y);
                MoveLines(y);
            }
        }
    }

    void MoveLines(int y)
    {
        for (int i = y; i < height; i++)
        {
            for (int x = 0; x < width; x++)
            {
                if (grid[x, y + 1] != null)
                {
                    grid[x, y] = grid[x, y + 1];
                    grid[x, y].gameObject.transform.position -= new Vector3(0, 1, 0);
                    grid[x, y + 1] = null;
                }
            }
        }
    }

    void DestroyLine(int y)
    {
        for (int x = 0; x < width; x++)
        {
            if (grid[x, y] != null)
            {
                Destroy(grid[x, y].gameObject);
            }
        }
    }

    bool CompleteLine(int y)
    {
        for (int x = 0; x < width; x++)
        {
            if (grid[x, y] == null)
            {
                return false;
            }
        }
        return true;
    }

    // Update is called once per frame
    void Update()
    {

    }

    public void SpawnTetromino()
    {
        float rng = Random.Range(0, 1f);
        rng *= tetrominos.Length;
        Instantiate(tetrominos[Mathf.FloorToInt(rng)], new Vector3(8, 25, 0), new Quaternion(0, 0, 0, 1));
    }

    //restarts game by pressing r
    [System.Obsolete]
    public void RestartGame()
    {
        if (Input.GetKeyDown(KeyCode.R))
        {
            Application.LoadLevel(Application.loadedLevel);
        }
    }
}
    
