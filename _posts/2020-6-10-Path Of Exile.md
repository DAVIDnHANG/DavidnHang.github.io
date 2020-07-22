---
layout: post
title: Path Of Exile
---

I will use CNN (Convolutional Neural Network) to classify images from the game in order to build an internal representation of the worlds.  The algorithm works as follows:
1. Grab still images from the game and pass it to CNN.
2. CNN predicts what is occurring in the still image.
3. These predictions pass to an internal map of the worlds.
4. Internal map of the world is then updated based on the latest predictions.
5. Give a present state of the internal map of the world.
6. Generate a series of actions.
7. These actions are then translated into mouse and keyboard input and sent to the mouse and keyboards.
8. This Loop will be repeated infinitely.

Visual Input
1. Use the projection matrix for the game is approximated.
  * determine the 3d coordinates that corresponds to 2d coordinates on the screen and visa-versa
  * Aw=p such that A is the projection Matrix, w is the matrix of world and p is matrix of projected points
  * to find the matrix of A, use several objects of fixed size in the game. Then
2. Manually, on a 800x600 resolution, approximate corner of the screen with a point and labeled with the corresponding world point

Conclusion:
 These are the changes needed to create the AI that plays games.

