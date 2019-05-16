# 3. Common Task Reference

Universal Driver provides a set of functions that cover most of the features on Diamond Systems' I/O boards. Each board contains a different set of features with different valid parameter ranges. Not all driver functions apply to all boards, so not all of the tasks described here apply to all boards. The board reference information in Chapter 10 lists each function applicable to each board, along with the relevant features and valid parameter ranges for the various functions. The function reference in Chapter 7.3 lists the boards associated with each function. Below is a list of common tasks that are explained in this chapter. User interrupts are explained in Chapter 6.

### **Task Summary**

* Performing an A/D. 
* Performs A/D conversions one at a time on one channel or a range of channels. 
* Performing an A/D Scan. 
* Performs A/D conversions in groups on a range of channels. 
* Interrupt-Based A/D Sample or Scan. 
* Performs A/D conversions using interrupts for faster sampling rates. 
* Performing a D/A Conversion. 
* Performs a D/A conversion on a specific channel. 
* Performing a D/A Conversion Scan. 
* Performs a D/A conversion on multiple, specified channels. 
* Interrupt-Based D/A Conversion Scan. 
* Performs D/A conversions using interrupt-based I/O. 
* Performing Digital I/O Operations. 
* Performs bit and byte read and write operations. 
* Checking Interrupt Operation Status. 
* Checks the status of the currently-running interrupt operation. 
* Performing an A/D Autocalibration. 
* Performs an A/D auto-calibration on a selected A/D mode or all A/D modes. 
* Performing a D/A Autocalibration. 
* Performs a D/A auto-calibration. 
* A/D Calibration Verification. 
* Checks the error in A/D LSB counts after calibration. 
* D/A Calibration Verification. 
* Checks the error in D/A LSB counts after calibration.

NOTE: In the step-by-step instructions for performing each task, it is assumed that you will already be making the proper calls to dscInit\(\), dscInitBoard\(\), dscFreeBoard\(\), and dscFree\(\) in your application.

