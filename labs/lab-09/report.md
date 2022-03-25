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

![image](https://user-images.githubusercontent.com/25308429/160159622-c6c8bce1-640f-4ce2-b0c8-297e01990467.png)

![image](https://user-images.githubusercontent.com/25308429/160159667-0e57ce36-6505-40d7-bf4d-0c99f1dd4e43.png)

And finally opening localhost:3000 in browser to view rocketchat:

![image](https://user-images.githubusercontent.com/25308429/160159834-4d882633-6893-4398-b3ac-c38b2d0b724c.png)

## Example 03

First I created a Dockerfile for this example, seen [here](https://github.com/emkulka/oss-repo-template/blob/master/labs/lab-09/DockerfileEX03),

then I ran the command `docker build -t helloworld .` (the output of which was *A LOT* so I'm not including a screenshot)

and finally I ran the command `docker run -p 5000:5000 helloworld` 

![image](https://user-images.githubusercontent.com/25308429/160162222-81650834-0271-4f34-a621-011c13d751b7.png)

![image](https://user-images.githubusercontent.com/25308429/160162306-ee27a73e-865e-4c1b-8312-17467bd1c9bc.png)

and went to localhost:5000

![image](https://user-images.githubusercontent.com/25308429/160162099-6d3b7cd4-eab6-4202-824a-010ab084db60.png)

## Example 04

First I created a Dockerfile for this example, seen [here](https://github.com/emkulka/oss-repo-template/blob/master/labs/lab-09/DockerfileEX04),

then I ran the command `docker build -t message-app .`

![image](https://user-images.githubusercontent.com/25308429/160172635-a1f09acb-5655-47d7-b9ad-c059077b2abb.png)

afterwards I ran the command `docker images` to view all available images (the message app has the red star next to it)

![image](https://user-images.githubusercontent.com/25308429/160173030-b2816a2b-94d8-4607-848e-826efc9563d0.png)

Since the message app was not linked to a batabase, it could not run. So the next step was to create the `docker-compose.yml` file, found [here](https://github.com/emkulka/oss-repo-template/blob/master/labs/lab-09/docker-compose.yml), so that both services could be launched at the same time.

Then I ran the commands `docker-compose build` to build 

![image](https://user-images.githubusercontent.com/25308429/160174540-faea20dc-6c84-4d5c-b040-d95b84e02066.png)

and `docker-compose up`


