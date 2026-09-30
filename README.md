# Airport Management System

## Introduction

The Airport Management System is a simple desktop application developed using Python and Tkinter. The main purpose of the project is to manage basic airport activities through one graphical interface.

The system allows the user to view flights, book tickets, cancel bookings, and view passenger details. It also keeps track of available seats and provides messages when the user enters incorrect or incomplete information.

This project was developed as a practical application of Python programming concepts. Instead of using concepts such as classes, functions, lists, dictionaries, loops, and conditions separately, they are combined here to create one working application.

## Problem Statement

Managing flight and passenger information manually can become difficult when bookings and cancellations need to be updated. A simple system is needed to keep flight information organized, record passenger bookings, update seat availability, and handle ticket cancellations.

The main goal of this project is to create an easy to use application that can perform these basic operations without requiring complicated software or a database.

## Main Features

The application has the following sections:

### Home

The home page displays a welcome message along with the total number of flights, current passengers, and available seats.

### Flights

The Flights section displays the available flights in a table. Each flight includes its flight number, airline, source, destination, departure time, and available seats.

### Book Ticket

The user can enter the passenger name, age, and phone number and then select a flight. The program checks the entered information and verifies that the selected flight has an available seat before completing the booking.

### Cancel Ticket

The user can cancel a booking by entering the passenger's name. If the passenger is found, the booking is removed and the available seat is restored.

### Passengers

The Passengers section displays the passengers who currently have bookings. It shows their name, age, phone number, flight number, and airline.

### Exit

The Exit option asks for confirmation before closing the application.

## Functional Requirements

The system should be able to:

1. Display the home page.
2. Show available flights.
3. Display basic system statistics.
4. Accept passenger details.
5. Allow the user to select a flight.
6. Check that required fields are filled.
7. Validate age and phone number.
8. Check seat availability.
9. Add passenger details after a successful booking.
10. Reduce the available seat count after booking.
11. Display booking confirmation.
12. Search for a passenger during cancellation.
13. Remove a cancelled booking.
14. Restore the available seat after cancellation.
15. Display passenger records.
16. Show warning and error messages.
17. Ask for confirmation before exiting.

## Non Functional Requirements

The application is designed to be simple and easy to use. The interface contains clear buttons and forms so that users can understand the available operations.

The application is also lightweight because it uses a small amount of data. Most operations are performed directly on Python lists and dictionaries, so they are quick.

The code is divided into different methods for different features. This makes it easier to understand and modify.

The current version does not require a database or additional external software apart from a Python installation with Tkinter.

## Algorithm

1. Start the program.
2. Create the Tkinter window.
3. Create the AirportManagementSystem object.
4. Load the predefined flight information.
5. Create an empty passenger list.
6. Create the header, menu, and main content area.
7. Display the home page.
8. Wait for the user to select an option.
9. If Flights is selected, display the flight table.
10. If Book Ticket is selected, collect passenger details and selected flight.
11. Check that all required fields are filled.
12. Check that age and phone number contain numbers.
13. Find the selected flight.
14. Check whether seats are available.
15. If a seat is available, reduce the seat count and save the passenger record.
16. If Cancel Ticket is selected, search for the passenger by name.
17. If the passenger is found, restore the seat and remove the passenger record.
18. If Passengers is selected, display the passenger records.
19. If Exit is selected, ask for confirmation and close the program.
20. Continue until the user exits.

## Flow Chart

```text
START
  |
  v
Open Application
  |
  v
Load Flights and Passenger List
  |
  v
Display Home Page
  |
  v
Select an Option
  |
  +---- Flights ----> Display Flight Details
  |
  +---- Book Ticket
  |          |
  |          v
  |     Enter Details
  |          |
  |          v
  |     Validate Input
  |          |
  |          v
  |     Check Seats
  |       /         | Available     Full
  |     |           |
  |     v           v
  |  Book Ticket  Show Error
  |
  +---- Cancel Ticket
  |          |
  |          v
  |     Find Passenger
  |       /         |    Found     Not Found
  |      |           |
  |      v           v
  | Cancel Ticket  Show Error
  | Restore Seat
  |
  +---- Passengers ---> Display Passenger Details
  |
  +---- Exit ---------> Confirm and Close
```

## Implementation Details

The application is written in Python and uses Tkinter for the graphical interface. The ttk module is used for widgets such as Treeview and Combobox, while messagebox is used for warnings, errors, confirmations, and information messages.

The main program is organized around the AirportManagementSystem class.

Some important methods are:

| Method | Purpose |
| --- | --- |
| create_header | Creates the application header |
| create_menu | Creates the navigation menu |
| create_main_area | Creates the main content area |
| show_home | Displays the home page |
| show_flights | Displays available flights |
| book_ticket_window | Handles ticket booking |
| cancel_ticket_window | Handles ticket cancellation |
| show_passengers | Displays passenger details |
| exit_program | Handles application exit |

Flight data is stored in a list of dictionaries. Each flight contains a flight number, airline, source, destination, departure time, and available seats.

Passenger information is stored in another list. Each passenger record contains the passenger name, age, phone number, and flight number.

## Ticket Booking

When the user selects Book Ticket, the program displays a form for passenger details.

The program first checks whether all fields have been filled. It then checks whether the age and phone number contain numeric values.

After that, the selected flight is identified and its available seats are checked.

If a seat is available, the program decreases the seat count by one and adds the passenger to the passenger list.

A confirmation message is then displayed with the booking details.

## Ticket Cancellation

For cancellation, the user enters the passenger name.

The program searches through the passenger list and compares the names without considering uppercase or lowercase differences.

If the passenger is found, the corresponding flight is identified. One seat is added back to that flight and the passenger record is removed.

If the passenger cannot be found, the program displays an error message.

## Testing

The main features were tested using both valid and invalid inputs.

| Test Case | Action | Expected Result |
| --- | --- | --- |
| Start application | Run the program | Home page opens |
| View flights | Click Flights | Flight table appears |
| Valid booking | Enter correct details | Ticket is booked |
| Empty field | Leave a field blank | Warning appears |
| Invalid age | Enter letters for age | Invalid age message appears |
| Invalid phone | Enter letters for phone | Invalid phone message appears |
| Full flight | Try booking with no seats | Flight full message appears |
| Valid cancellation | Enter an existing passenger | Booking is cancelled |
| Invalid cancellation | Enter an unknown passenger | Not found message appears |
| Passenger list | Open Passengers | Passenger record is displayed |
| Exit | Click Exit | Confirmation appears |

Testing these cases helped check both the normal working of the application and its response to incorrect input.

## Challenges Faced

One of the main challenges was keeping the passenger information and flight seat information synchronized.

When a ticket is booked, the passenger needs to be added to the passenger list while the available seats for that flight need to decrease. During cancellation, the passenger needs to be removed and the seat needs to be restored.

Input validation was another important part of the project. The user may leave a field empty or enter letters where numbers are expected, so the program needs to handle these situations properly.

Creating the graphical interface was also different from writing a normal Python program because the application responds to actions such as button clicks and selections. This helped in understanding event driven programming.

## Learning and Key Takeaways

This project helped me understand how different Python concepts can be combined to create a complete application.

The main concepts I practiced were:

- Creating a GUI using Tkinter
- Using classes and objects
- Using functions to organize code
- Working with lists and dictionaries
- Searching through stored records
- Using conditions for validation
- Connecting buttons to functions
- Handling user input
- Updating data after booking and cancellation
- Displaying records using Treeview
- Using message boxes
- Testing different user scenarios

The project also helped me understand that a program should handle incorrect input properly instead of only working when everything is entered correctly.

## Limitations

The current version has some limitations.

- Passenger data is stored only while the program is running.
- Bookings are lost when the application is closed.
- Flights are predefined.
- There is no database.
- There is no login or administrator system.
- Tickets cannot currently be printed or downloaded.
- Cancellation is based on the passenger name.
- There is no actual payment system.

## Future Improvements

The project can be improved by adding a database such as SQLite or MySQL so that passenger and flight information can be stored permanently.

Other possible improvements include:

- User and administrator login
- Admin panel
- Add, remove, and update flight functionality
- Unique booking IDs
- Travel dates
- Seat numbers
- Ticket generation
- Booking history
- Passenger search
- Better phone number validation
- Payment simulation
- More detailed flight management

## Conclusion

The Airport Management System is a simple Python GUI project that demonstrates the basic workflow of an airport ticket management system.

The application can display flights, book tickets, cancel bookings, update available seats, and display passenger information.

The project provided practical experience with Python GUI development, classes, functions, data structures, input validation, event handling, and testing.

Although the current version is basic, it provides a useful foundation for adding features such as database storage, authentication, dynamic flight management, and ticket generation.

## Project Structure

```text
Airport Management System/
|
|-- airport_management_system.py
|-- README.md
|-- project_report.docx
```

## How to Run

Make sure Python 3.x is installed on the system.

Check the installation using:

```bash
python --version
```

Open the project folder and run:

```bash
python airport_management_system.py
```

The Airport Management System window will open.

## Requirements

The project uses Python's built in libraries.

```text
Python 3.x
Tkinter
ttk
```

No external database or package installation is required for the current version.

## Project Information

| Detail | Information |
| --- | --- |
| Project Name | Airport Management System |
| Language | Python |
| GUI | Tkinter |
| Application Type | Desktop Application |
| Data Storage | In memory lists and dictionaries |
| Project Type | Academic / Learning Project |
