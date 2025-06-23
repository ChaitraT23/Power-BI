KSTBF ROOMS BOOKING DASHBOARD
Project Overview
The KSTBF Department Room Booking System is an internal web-based application designed to streamline the reservation and management of rooms within the KSTBF. This system allows Staff, Students, and Public to easily book rooms for meetings, seminars, workshops, and other academic or departmental events.
PowerBI/ROOMS_UPDATED.pdf at main · ChaitraT23/PowerBI

Steps followed
Step1: Collect data from databases (SQL Server, Excel.)
Step2: Use Power Query Editor to import and preview datasets.
Step3: Convert date fields (check-in, booking date) to proper date types, Remove duplicates, nulls, and errors.
Step4: Create new columns 
Year from Application Date: Year = YEAR([booking_date])
Calculate Cancelled Amount using condition: Cancelled Amt = IF([IsCancelled]=1, [CancelledAmt], 0)
Step5: Link tables using foreign keys (e.g., UserID, DeptID, AppID).
Step6: Create KPIs using DAX formulas:
Total Applications = COUNT([ApplicationID])
Tot Rooms Booked = SUM([RoomCount])
Total App Cost = SUM([Cost])
Cancelled App = CALCULATE(COUNT([AppID]), [IsCancelled]=1)
Cancelled App Amt = CALCULATE(SUM([CancelledAmt]), [IsCancelled]=1)
Step7: Cross-check KPIs with raw data
 Check filter interactions (e.g., gender filter impacts total).
