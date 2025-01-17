# Lab 08 - Testing and Continuous Integration

## Checkpoint 1

Built using command `make` after generating in ccmake (as per Prof. Turner's guidance)
![image](https://user-images.githubusercontent.com/25308429/159069993-320e46a0-b22a-42cd-8fcc-77c8eaa33c31.png)

## Checkpoint 2

Find the Nightly and Experimental sections and look at some of the submissions. How can you see what tests were run for a particular submission?
- Under the Test section of each table, you will see how many tests were (and were not) run. Additionally, if you click on the number under the Fail or Pass columns, it will show you the specific tests that passed or failed, respectively.

Find a submission with errors. Can you see what the error condition was? How does this help you debug the failure?
- I looked at the site DESKTOP-UJLHUPM under Experimental. The error was `*** ERROR executing: No such file or directory`. You may be able to debug this by ensuring all directories are created and referenced properly.

Find a system that is close to your specific configuration in the _Nightly_, _Nightly Expected_ or one of the _Masters_ sections. How _clean_ is the dashboard? Are there any errors that you need to be concerned with?
- I looked at the site cmake-wm03.nvidia since it uses Ubuntu 18.04 like I do. This dashboard is very clean, with no errors, and all 682 of the tests that ran passed. There is no sign of concerning errors.

Screenshot of my test submission on the Experimental dashboard

![image](https://user-images.githubusercontent.com/25308429/159100924-b453049d-9680-4b18-9097-ade5ef324826.png)

There are no errors, which is consistent with other projects using a similar architecture.

## Checkpoint 3

screenshot from command line of inital test with errors

![image](https://user-images.githubusercontent.com/25308429/159101279-45a1cf4b-b25a-41cc-a1a9-db25cb4b5778.png)

Examining the updated Copyright.txt, I can see that some of the Contributors were removed and the copyright ending year is 2020 instead of 2022. By fixing these issues, the tests run as expected and pass.

screenshot from command line of error fix and successful run

![image](https://user-images.githubusercontent.com/25308429/159101654-e501f68e-36b9-41f0-9371-2020573b790d.png)

## Checkpoint 4

[Repository link](https://github.com/emkulka/OSS-lab08-ch4)

![image](https://user-images.githubusercontent.com/25308429/159104293-07e9c4c5-a565-40d4-a9db-b6de35cf7083.png)

![image](https://user-images.githubusercontent.com/25308429/159104359-668211ff-c4fa-456f-aed2-e139398fc6e8.png)


