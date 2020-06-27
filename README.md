//# some-c-code
//bruh


using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{

    public float ForwardForce = 2000f;

    public float gravity = -9.18f;

    public Transform transformm;

    public CharacterController controller;

    public Rigidbody rb;

    Vector3 velocity;


    private void Update()
    {
        float x = Input.GetAxis("Horizontal");
        float z = Input.GetAxis("Vertical");

        Vector3 move = transformm.right * x + transformm.forward * z;

        controller.Move(move* ForwardForce * Time.deltaTime);

        velocity.y += gravity * Time.deltaTime;

        controller.Move(velocity * Time.deltaTime);
    }
}
//this is some code meant to be run in unity game engine
