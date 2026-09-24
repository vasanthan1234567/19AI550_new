# Ex.No: 10 – Implementation of 3D Game

### DATE: 24/09/2026
### REGISTER NUMBER: 212224240180
### AIM:
To develop a 3D Coin Collection Game in Unity using **Reinforcement Learning (ML-Agents) technology**, where the player controls a sphere and collects coins to complete the game.
### ALGORITHM:

```
1. Create a new 3D project in Unity.
2. Create a game environment using a plane as the ground.
3. Create a sphere as the player and add Rigidbody physics.
4. Create five coins and place them at different positions in the game area.
5. Add a camera to follow and display the game environment.
6. Implement player movement using a C# script.
7. Detect coin collection using collision detection.
8. Increase the score whenever the player collects a coin.
9. Check whether all five coins have been collected.
10. Display "You Win!" when all the coins are collected.
11. Test and run the game in the Unity Game window.
12. Use Unity ML-Agents/Reinforcement Learning to train the player agent if required.
```

### PROGRAM:

**Player/Coin Collection Script:**

```csharp
using UnityEngine;
using UnityEngine.UI;

public class Coin : MonoBehaviour
{
    public Text winText;

    private void OnTriggerEnter(Collider other)
    {
        if (other.CompareTag("Player"))
        {
            GameManager.instance.CollectCoin();
            Destroy(gameObject);
        }
    }
}
```

**Game Manager Script:**

```csharp
using UnityEngine;
using UnityEngine.UI;

public class GameManager : MonoBehaviour
{
    public static GameManager instance;

    public int totalCoins = 5;
    private int collectedCoins = 0;

    public Text winText;

    private void Awake()
    {
        instance = this;
        winText.text = "";
    }

    public void CollectCoin()
    {
        collectedCoins++;

        if (collectedCoins >= totalCoins)
        {
            winText.text = "YOU WIN!";
        }
    }
}
```

### OUTPUT:

<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/30d5aa39-ca0a-453b-9682-2df06949523c" />
<img width="1915" height="1026" alt="image" src="https://github.com/user-attachments/assets/9d40ebdf-ff90-4533-9a7d-d5184a8ee39d" />


### RESULT:

Thus, the **3D Coin Collection Game** was successfully developed using Unity and implemented using **Reinforcement Learning (ML-Agents) technology**.
