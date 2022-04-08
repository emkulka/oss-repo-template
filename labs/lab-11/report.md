# Lab 11 - Tensorflow

## Checkpoint 1: Verify Your TensorFlow

After running the given code segment, this was the pop-up window I received.

<img src="https://user-images.githubusercontent.com/25308429/162220149-10ea96ec-65e6-4d64-977a-02a7cda68ad1.png" width="300" height="300" />

## Checkpoint 2: Run a TensorFlow classification

After completing the fashion classification example, I then modified the specified block of code to produce information for images 9000-9014 rather than images 0-14. Here is the screenshot of that plot

<img src="https://user-images.githubusercontent.com/25308429/162256097-5ae4a943-773f-4823-a1c4-b6d4493147f9.png" width="450" height="300" />

## Checkpoint 3: Curate some data

### Image 1 - Pullover

Original image:

<img src="./images/pullover.JPG" width="200" height="150" />

Greyscale, inverted, 28x28 image:

<img src="./images/pullover_processed.png" />

Classification results:

<img src="https://user-images.githubusercontent.com/25308429/162356537-22b97c95-0e7b-4dc4-874e-89063127914a.png" width="350" height="300" />

```
[[1.2203583e-02 1.7796726e-06 9.2843950e-01 1.0356769e-06 3.1591386e-02
  9.0163560e-08 2.7739819e-02 3.0974385e-09 2.2757335e-05 5.8823471e-09]]
2
Pullover
```

### Image 2 - Dress

Original image:

<img src="./images/dress.JPG" width="175" height="150" />

Greyscale, inverted, 28x28 image:

<img src="./images/dress_processed.png" />

Classification results:

<img src="https://user-images.githubusercontent.com/25308429/162356737-0b04bfbe-de09-4f43-9ed7-31130514a3b8.png" width="350" height="300" />

```
[[7.47589618e-02 5.97069389e-04 3.68908769e-03 8.13899875e-01
  3.31244461e-04 2.24307631e-04 1.05990596e-01 3.41750965e-05
  2.26665099e-04 2.48004770e-04]]
3
Dress
```

### Image 3 - Ankle Boot

Original image:

<img src="./images/ankleboot.JPG" width="150" height="150" />

Greyscale, inverted, 28x28 image:

<img src="./images/ankleboot_processed.png" />

Classification results:

<img src="https://user-images.githubusercontent.com/25308429/162356843-141fcbe6-bf39-44ae-b4c7-ec8a02cd239b.png" width="350" height="300" />

```
[[2.3864158e-03 2.1092386e-03 3.1962243e-03 5.1720999e-04 1.1321499e-03
  3.3819322e-08 1.1932800e-01 1.9585585e-07 8.7132651e-01 4.0202899e-06]]
8
Bag
```
