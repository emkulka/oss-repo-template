# Lab 09 - Virtualization and Docker

## Example 00

The first step of this example was to install Docker. I completed this at the end of lecture on Tues 3/22. 

The second step of this example was to run the command `docker run docker/whalesay cowsay boo`. This was the result:

![image](https://user-images.githubusercontent.com/25308429/160140871-e7910531-fbcb-4c7c-afb7-f003331cc1b7.png)

## Example 01

The first step was to run the command `docker run -it ubuntu bash`. Upon doing so, my Ubuntu terminal then looked like this:

![image](https://user-images.githubusercontent.com/25308429/160142921-22873401-7aea-4840-82a4-8699fa61a27e.png)

I am now in the Ubuntu terminal running in the docker container with ID `bee7885e78b3`.

here is what this docker looks like in the desktop app: 

![image](https://user-images.githubusercontent.com/25308429/160143459-48b32b1e-26d3-45e5-b12f-4ff9be85ece6.png)

After installing vim via `apt update` and `apt install vim`, I created a test file in the root directory.

![image](https://user-images.githubusercontent.com/25308429/160145155-7adf629e-c864-4f19-b45c-029d82aa0555.png)

Finally I installed `cowsay` and followed the instructions on how to successfully run `cowsay`:

![image](https://user-images.githubusercontent.com/25308429/160145844-eb85a695-104b-4087-9f29-9da83d628832.png)

## Example 02

Running the command `docker run --name db -d mongo:3.2 mongod --smallfiles`:

![image](https://user-images.githubusercontent.com/25308429/160150323-c9279840-e892-4dfe-a135-794d49ee9bad.png)

![image](https://user-images.githubusercontent.com/25308429/160150516-14a4b5c4-ccd7-4665-9246-9c0f4c6d6465.png)

Followed by running the command `docker run --name rocketchat -p 3000:3000 --env ROOT_URL=http://localhost --link db:db -d rocket.chat:0.62`:

![image](https://user-images.githubusercontent.com/25308429/160150944-260b0000-b5c3-4326-8763-7d19c257a637.png)

![image](https://user-images.githubusercontent.com/25308429/160150992-d39f18eb-b6a6-4ee7-9a1d-c48004a0764b.png)

And finally opening localhost:3000 in browser to view rocketchat:

## Example 03

(insert steps, observations, etc.)

## Example 04

(insert steps, observations, etc.)

