# Exp02-RollABall

## Name: Tanessha Kannan
## Register Number: 212223040225

## Aim:
To develop a 3D application to roll a ball in unity

## Algorithm:
### Steps:
**Step1:** File -> Scene -> Select the scene -> Save as-> New folder(Scenes)-> File name (MiniGame)

**Step2:** Heirarchy -> 3D Object-> Plane 
[ Right side-> Inspector-> Change the name of plane (Name: Ground) ,Transform -> Reset ,Edit -> FrameSelected ]

**Step3:** Scale the ground by giving the scaling value as x=4 y=1 z=4

**Step 4:** Heirarchy -> 3D Object-> Sphere [ Right side-> Inspector-> Change the name of plane (Name: Player)
Transform -> Reset , Edit -> FrameSelected, Transform -> Position -> y=0.5]

**Step5:** Hierarchy -> DirectionalLight [ Inspector -> Change the color to white (255,255,255)]

**Step 6:** Create a folder in project and name as Materials [Material folder -> Create -> Material (Name: Background)
Inspector ->Surface Inputs ->BaseMAp (Choose the color) Metallic map-> 0, Smoothness -> 0.25, Drag the Background to the plane and release the mouse
Material folder -> Create -> Material (Name: Sphere) Inspector ->Surface Inputs ->BaseMAp (Choose the color) Metallic map-> 0,Smoothness -> 0.75,Drag the Sphere material to the ball and release the mouse

**Step7:** Hierarchy -> Player-> Inspector ->Add component-> Rigidbody

**Step8:** Create a new script -> Create a folder in project (Name: Scripts) Hierarchy -> Player -> Inspector-> AddComponent-> NewScripts-> PlayerController( Click create and Add), Copy the PlayerController and drag to Script folder, Double click the PlayerController file and type the coding

## Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class RollTheBall : MonoBehaviour
{
    public float xforce = 5.0f;
    public float yforce = 100.0f;
    public float zforce = 5.0f;    
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        float x = 0.0f, y = 0.0f, z = 0.0f;
        if (Input.GetKey(KeyCode.A))
        {
            x = x - xforce;
        }
        if (Input.GetKey(KeyCode.D))
        {
            x = x + xforce;
        }
        if (Input.GetKey(KeyCode.W))
        {
            z = z + zforce;
        }
        if (Input.GetKey(KeyCode.S))
        {
            z = z - zforce;
        }
        if (Input.GetKey(KeyCode.Space))
        {
            y = y + yforce;
        }
        if (Input.GetKey(KeyCode.LeftControl))
        {
            y -= yforce;
        }
        GetComponent<Rigidbody>().AddForce(x, y, z);
    }
}
```
## Output:
<img width="1110" height="480" alt="Screenshot 2025-10-04 225112" src="https://github.com/user-attachments/assets/a3a4c61c-74d9-4739-ae4a-a8c854d9894b" />

## Result:
A 3D application to roll a ball in unity is developed
