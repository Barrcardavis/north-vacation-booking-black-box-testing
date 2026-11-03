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
<img width="4032" height="1299" alt="image" src="https://github.com/user-attachments/assets/208ff597-cff3-4244-a4d9-abe41f8a1334" />



Classification	Partition	Range or Condition	Expected ResultNumber of Guests	Invalid Low	Fewer than 1 guest	ValueError
Number of Guests	Valid Standard Rate	1–5 guests	No additional guest fee
Number of Guests	Valid Additional Fee	6–12 guests	Additional $25 per guest per night
Number of Guests	Invalid High	More than 12 guests	ValueError
Check-in and Checkout Dates
Classification	Partition	Range or Condition	Expected ResultDates	Invalid	Check-in date equals checkout date	ValueError
Dates	Invalid	Check-in date after checkout date	ValueError
Dates	Valid	Check-in date before checkout date	Reservation accepted
Availability
Classification	Partition	Range or Condition	Expected ResultAvailability	Valid	Every requested night is available	Reservation accepted
Availability	Invalid	One or more nights unavailable	UnavailableError
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
