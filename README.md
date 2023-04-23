Download Link: https://assignmentchef.com/product/solved-assignment
<br>
<p class="ui header product-top-header" title="Assignment Solution">Use ONLY pointer arithmetic and pointer notation in the implementation

Output file:You should create two files:1. BadOutput.txt which will have the contents of the input file. You will just write back the contents into this file2. GoodOutput.txt should contain the records of account numbers, corresponding amounts and designations which conform to the requirements. It should be grouped in the order of designation as shown in the sample file. All the ‘J’s must come first, followed by the ‘S’s and then come the ‘M’s.

Implement following functions:bool bonusWriteData(char *,int *,double *,char *,int):

char *-Takes the filename – GoodOutput.txtint * – integer pointer for account IDsdouble * – double type pointer for amountschar * – character pointer to hold designations

In this function, you will sort the records based on the ascending order of the amounts and the you will print them below the existing data in GoodOutput.txt file. Then calculate the least amount which is greater than or equal to the average value of the amounts and the greatest amount which is lesser than or equal to the average value of the amounts. You can (recommended) write 2 separate functions to perform this operation. Return false if unable to open the file for appending, else write all the requested info and return true.

bool load_data(char*, int *, double *,char *, int ): This function takes the input file name, integer, double and character pointers and the size as integer. It opens the input file. If unable to open it, returns false. Otherwise load the account information from the text file into the integer, double and character arrays and return true at the end. The first char pointer is the string holding the name of the file to open, int * is the account ID array, double * is the amount array, the second char * is the designation array and the last int is the size or the number of records. Use fscanf or other library functions to read in the data.void print_data(int *, double *, char *, int): This function takes integer array , double array, character array and the integer size and displays the data on the console stored in these arrays as shown in the sample output below. Use proper output formatting and heading to display the output. Remember this function prints the data on the screen.

int highest_amount(double *, int): This function takes the double amounts pointer and the number of accounts. It finds the highest amount and returns the index corresponding to the highest amount.

int lowest_amount(double *, int): Same as above function except it returns the index corresponding to the lowest amount.

float average_amount(double *, int): Same as above functions except it returns the average amount for all the accounts.

bool write_data(char* , int *, double *, char *, int): This function writes the account information (account IDs, amounts and designations) into a text file (BadOutput.txt and GoodOutput.txt). Following are the arguments passed to this function

char*- output file name.int*- pointer containing account IDs information.double*- pointer containing amount information.char* – pointer containing the designation information.int – denoting the number of records which need to be printed.

if unable to open the file in w mode return false else write the data and then return true at the end. Use fprintf or other library function to write the data into the text file.This function is called twice, once to print raw data and another time to print the cleaned-up data.

int check_palindrome(int ): Takes an integer and checks if the integer is a palindrome, if it is then return 1 else return 0. A palindrome is a number which has the same value when reversed. Example:5005, 1111, 1221 7117 etc.

int clean_data(int *, double*, char*, int *, double *, char *, int):

int * – pointer containing original all account IDs informationdouble * – pointer containing original all amounts informationchar* – pointer containing original all designation information

int * – pointer to hold the valid account IDs informationdouble * – pointer to hold the corresponding valid amounts informationchar * – pointer to hold the corresponding valid designation information.

int – original sizereturns int – count of the valid number of IDs.

All the records which conform to the criteria must be used to fill the second set of int*, double* and char* pointers and then at the end return the count of such valid rows.

In this function, you will loop through the original records and find all those which match the criteria specified and then copy them over to the new set of valid pointers. To do this you should check if each account number is a palindrome (call check_palindrome function on each original ID) and if the corresponding amount value is exactly between $500 and $5000.00 inclusive and the corresponding designation is anything other than P, if these matches then copy that information into the new set of pointers correspondingly and at the end return how many such valid records were copied over. One of the major problems you will run across is indexing, remember that the new valid pointers should start from 0 and must be incremented after every time a new record is added.

void sort_data(int *,double *,char *, int):int * – Integer pointer holding all the valid account IDsdouble * – Double pointer holding all the corresponding valid amountschar * – Character pointer holding all the corresponding valid designationsint – count of the number of valid records (remember this cannot be 13 anymore)

Now, you need to group them based on the designations, the first group must have the J and then the second group must have the S and the last group must be the M. Remember you are not sorting anything in ascending or descending order, you are group sorting them. When you swap the positions of designations while grouping, make sure the account IDs and the amounts match too after the grouping.

int main(int argc, char *argv[]):Use command line arguments to get the file names and the original number of accounts. Use the variable argc to check if there are enough inputs provided by the user. If not, display an error message and terminate the program. Get the size from command line using atoi. Allocate space to an integer, double and a character pointer using malloc to store the original records. Also, allocate another set of integer, double and character pointers to store the valid records (while doing this assume all the original records are valid, so the size for malloc will still be 13).Call the load_data function, print_data function and call the highest_amount, lowest_amount and the average_amount functions to print all the stats (max, min and avg). Call the write_data function to write the original set of records into the BadOutput.txt file. Look at the file on blackboard for reference.Call the clean_data function to clean-up the records. This function returns a number denoting the valid number of records present after ignoring the ones which didn’t satisfy the criteria. Call the sort_data function by sending the valid pointers (int,double,char and the valid size), this will group your records based on the designations. Call the print_data function by sending the valid pointers to print the cleaned data which is now grouped by designations. Call the highest_amount, lowest_amount and the average_amount functions on the valid amounts pointer and print the results as shown in the sample output below. After doing this then call the write_data function to write the cleaned set of records into the GoodOutput.txt file. Remember, your valid records must be sorted (grouped by designations) both on the screen as well as on the GoodOutput.txt file.At the end, free the space allocated to the:2 integer type pointers2 double type pointers2 char type pointers using the function free ().Show proper error messages and output messages as and when necessary and must be formatted correctly.Flow should be:Create pointers (6) Open file and load data then print them along with stats write the original records to the BadOutPut.txt file Update the records correctly (clean_data) sort (group them according to the designations) print the data again with stats Then write the data onto GoodOutput.txt file Free the memory allocated for the pointersprint_data function will come in very handy. So, use it extensively while writing your program.Sample Output

:~$ compile 3.c:~$ ./a.out

USAGE ERROR — ARGUMENT COUNT MUST BE 5 //CHECK ARGC ERROR

:~$ ./a.out Input.txt

USAGE ERROR — ARGUMENT COUNT MUST BE 5

:~$ ./a.out 13 Input.txt

USAGE ERROR — ARGUMENT COUNT MUST BE 5

:~$ ./a.out 13 3.txt BadOutput.txt GoodOutput.txt //CHECK FILENAME ERROR

Unable to open the input file 3.txt for load dataExiting!!!

:~$ ./a.out 13 Input.txt BadOutput.txt GoodOutput.txt

ACCOUNTS AMOUNTS DESIGNATION1001 1591.63 M1011 1503.54 S2002 2000.43 M3332 2567.99 J2112 3112.67 M4334 5111.34 S6134 7172.23 P9009 4999.00 P3003 4000.00 S4004 5000.00 S5005 3000.00 J6116 4599.91 S7007 2890.58 J

The TA with ID 6134 has the maximum amount of 7172.23 from the original file data

The TA with ID 1011 has the minimum amount of 1503.54 from the original file data

The average amount across all the TAs is 3657.64

Data from Input.txt is now written to BadOutput.txt

*********DATA AFTER CLEANING********

ACCOUNTS AMOUNTS DESIGNATION7007 2890.58 J5005 3000.00 J3003 4000.00 S4004 5000.00 S6116 4599.91 S2002 2000.43 M1001 1591.63 M2112 3112.67 M

The TA with ID 4004 has the maximum amount of 5000.00 from the updated file data

The TA with ID 1001 has the minimum amount of 1591.63 from the updated file data

The average amount across all the TAs is 3274.40

Updated output written to GoodOutput.txt

Bonus appended to GoodOutput.txt

:~$ ./a.out 13 Input.txt BadOutput.txt GoodOutput.txt

ACCOUNTS AMOUNTS DESIGNATION //RED DENOTES INVALID1001 1591.63 M1011 1503.54 S2002 2000.43 M3332 2567.99 J2112 3112.67 M4334 5111.34 S6134 7172.23 P9009 4999.00 P3003 4000.00 S4004 5000.00 S5005 3000.00 J6116 4599.91 S7007 2890.58 J

The TA with ID 6134 has the maximum amount of 7172.23 from the original file data

The TA with ID 1011 has the minimum amount of 1503.54 from the original file data

The average amount across all the TAs is 3657.64

Data from Input.txt is now written to BadOutput.txt

*********DATA AFTER CLEANING********//LOOK AT DESIGNATION IT IS GROUPED &amp; ORDERED as J’s first, S’s next and M’s next

ACCOUNTS AMOUNTS DESIGNATION7007 2890.58 J5005 3000.00 J3003 4000.00 S4004 5000.00 S6116 4599.91 S2002 2000.43 M1001 1591.63 M2112 3112.67 M

The TA with ID 4004 has the maximum amount of 5000.00 from the updated file data

The TA with ID 1001 has the minimum amount of 1591.63 from the updated file data

The average amount across all the TAs is 3274.40

Updated output written to GoodOutput.txt

<span class="kksr-muted">Rate this product</span>