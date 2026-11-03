# north-vacation-booking-black-box-testing

Learning Practice: Black-Box Testing, Part 1

Step 1: Equivalence Partitions
Test Classifications
Number of nights
Number of guests
Check-in and checkout dates
Availability

Step 2: Equivalence Partition Tables
Number of Nights
<img width="763" height="154" alt="image" src="https://github.com/user-attachments/assets/c0649575-0d7a-41f2-ae95-34572069fb76" />


Number of Guests
<img width="770" height="211" alt="image" src="https://github.com/user-attachments/assets/82e90694-3767-4a43-9e4e-67de8d8a878d" />


Check-in and Checkout Date
<img width="766" height="151" alt="image" src="https://github.com/user-attachments/assets/6413d121-e4d9-464a-8bed-df370daf2127" />


Available
<img width="768" height="114" alt="image" src="https://github.com/user-attachments/assets/2ec50362-2327-4ae1-9c20-6321ab1b0093" />

Step 3: Test Cases
TC01
Classification: Number of Nights
Partition: Invalid Low
Input: 0 nights
Expected Result: ValueError
TC02
Classification: Number of Nights
Partition: Valid
Input: 7 nights
Expected Result: Reservation accepted
TC03
Classification: Number of Nights
Partition: Invalid High
Input: 32 nights
Expected Result: ValueError
TC04
Classification: Number of Guests
Partition: Invalid Low
Input: 0 guests
Expected Result: ValueError
TC05
Classification: Number of Guests
Partition: Valid Standard Rate
Input: 4 guests
Expected Result: Reservation accepted with no additional guest fee
TC06
Classification: Number of Guests
Partition: Valid Additional Fee
Input: 8 guests
Expected Result: Reservation accepted with additional guest fee for 3 guests at $25 per guest per night
TC07
Classification: Number of Guests
Partition: Invalid High
Input: 13 guests
Expected Result: ValueError
TC08
Classification: Check-in and Checkout Dates
Partition: Invalid
Input: Check-in = July 10, Checkout = July 10
Expected Result: ValueError
TC09
Classification: Check-in and Checkout Dates
Partition: Invalid
Input: Check-in = July 15, Checkout = July 10
Expected Result: ValueError
TC10
Classification: Check-in and Checkout Dates
Partition: Valid
Input: Check-in = July 10, Checkout = July 15
Expected Result: Reservation accepted and calculated as 5 nights
TC11
Classification: Availability
Partition: Valid
Input: All requested nights available
Expected Result: Reservation accepted
TC12
Classification: Availability
Partition: Invalid
Input: At least one requested night unavailable
Expected Result: UnavailableError
Notes on Equivalence Partitioning

Equivalence partitioning reduces the number of tests needed by grouping inputs that should produce the same behavior. Instead of testing every possible value, one representative value is selected from each valid and invalid partition. This provides good test coverage while minimizing the total number of test cases.
