4.1
Suppose you just cloned a repository that included one python file, my_first_file.py, and you now want to add a second file to your repository named my_second_file.py and push it to Github.com. Complete the sequence of linux shell commands:
		
	git clone git@github.com:my-name/my-imaginary-repo.git
	##complete the sequence
	touch my_second_file.py
	git add my_first_file.py my_second_file.py
	git commit -m "Plz"
	git push

4.2
Describe the workflow you adopted for this lab (i.e. did you develop on your VM and push/pull to get code to your RPi, did you edit files directly on your RPi, etc.).  Are there ways you might be more efficient in the next lab (i.e. learning a text-based editor so you can edit natively on the RPi, understanding Git commands better, etc.)?

I edited my code on the VM and pushed the files to git and pulled the fills from git to the RPi. I can try to master the usage of nano/vim to increase the efficiency because I can simply edit the code on the terminal. I could also write a script that concatenates all of the git commands so that they will run at once.

4.3
In the starter code, we added a 200 ms sleep. Suppose you needed to poll the ultrasonic ranger as fast as possible, so you removed the sleep function. Now, your code has just the function ultrasonicRead() inside a while loop. However, even though there are no other functions in the while loop, you notice there is a constant delay between each reading. Dig through the python library to find out why there is a constant delay. What is the delay amount? In addition, what communication protocol does the Raspberry Pi use to communicate with the Atmega328P on the GrovePi when it tries to read the ultrasonic ranger output using the `grovepi` python library?

The UltrasonicRead function has a built-in delay, which calls the function "time.sleep(.06)". Also, there is a firmware delay for about 50ms. Therefore, there is a delay in the reading even if the 200-ms delay is deleted in the main file.

It is using a I2C communication protocol.

