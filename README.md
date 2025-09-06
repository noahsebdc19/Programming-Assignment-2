# Programming Assignment 2

This exercise illustrates how to utilize the NumPy module in Python to address two problems that highlight its fundamental features. The exercises are designed to be straightforward, allowing learners to grasp the concepts with confidence. 

The first problem focuses on normalization, a crucial preprocessing step in data analytics. Normalization is important as it helps to bring all the features to a similar scale, which is a common requirement for many machine learning algorithms. It involves creating a random 5x5 array and adjusting its values to center around zero, followed by scaling them according to their spread. 
The second problem entails finding values divisible by three. This involves constructing a 10x10 array using the squares of the first 100 integers. 

These exercises are designed to teach learners how to use NumPy to store results, perform mathematical operations, and create arrays. These are not just skills, but essential tools for effectively managing and analyzing data, making the learning process more motivating and rewarding.

# 1. Normalization Problem
Normalization is a crucial step in data processing as it allows for comparing different values, simplifying the analysis process. When a dataset contains extremely large or small quantities, analysis becomes more challenging. To address this issue, normalization involves adjusting the data so that the average (mean) becomes zero and then scaling it such that the standard deviation (or range of values) equals one. To illustrate this process, you can create a random 5x5 dataset, compute its mean and standard deviation, and then normalize it. Maintaining a consistent scale throughout this procedure prepares the data for more effective analysis.

	#Normalization Problem

	import numpy as np
 

	# Create a random 5x5 array (values between 0 and 1)
 
	X = np.random.random((5, 5))
 

	# Find the mean (average) of all elements in X
 
	mean_X = X.mean()
 

	# Find the standard deviation (how spread out the values are)
 
	standard_dev_X = X.std()
 

	# Apply the normalization formula
	# Z = (X - mean) / standard deviation
	# This makes the new data have mean ~0 and std ~1
 
	Z = (X - mean_X) / standard_dev_X
 

	# Save the normalized array
 
	np.save("X_normalized.npy", Z)
 

	# Print results
 
	print("Original X: \n", X)                # show the random 5x5 array
 
	print("\nMean:", mean_X)                  # show the mean
 
	print("Standard Deviation:", standard_dev_X)  # show the std
 
	print("\nNormalized X (Z): \n", Z)        # show the normalized array


# 2. Divisible by 3 Problem

The squares of the first 100 positive integers are organized into a 10×10 matrix for this task. The goal is to identify the square numbers that are divisible by three. The program's key step is using the modulo operation to separate integers that can be evenly divided by three from those that cannot. Finally, the selected values are saved to a file. This technique illustrates filtering and arranging data using NumPy according to specific requirements.

	#Divisible by 3 Problem

	import numpy as np
 

	# Create an array of integers from 1 to 100
 
	numbers = np.arange(1, 101)  
 

	# Square each integer in the array
 
	squares = numbers**2  
 

	# Reshape the squared values into a 10x10 matrix
 
	A = squares.reshape(10, 10)  
 

	# Select only the squared numbers that are multiples of 3
 
	div_by_3 = squares[squares % 3 == 0]  
 

	# Save the divisible-by-3 results into a .npy file
 
	np.save("div_by_3.npy", div_by_3)  
 

	# Display the numbers divisible by 3
 
	print(div_by_3)  
