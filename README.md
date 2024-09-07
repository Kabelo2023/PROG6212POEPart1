1. Purpose of the Application:
This application's objective is to assist Monash University in planning and monitoring a variety of campus activities. Users can register for events, inform students, retrieve data from outside sources, and examine event details in addition to filtering events by department. This WPF application offers a straightforward interface for controlling campus activities and is made to be user-friendly.

2. Important characteristics:
Event Filtering: The list of events can be filtered by department (such as science, arts, or engineering). LINQ is used to achieve this filtering, making it possible to efficiently query and filter the event list according to the department of choice.

Event Display: A ListView control including columns for the event name, date, kind, and department is used to display the events. The ListView makes it simple for visitors to browse through the events by displaying the list in an orderly and streamlined manner.

Event Details Section: The name, date, kind, and department of an event are shown in a section on the right side of the window when a user chooses it from the list. This expands the user's knowledge about the event without overcrowding the primary list of events.


User Actions:

Register for Event: Users can sign up for an event by clicking on a button. The logic for event registration can be extended to accommodate real registration processes, even if it is currently emulated with a straightforward message box.
Notify Students: Pressing this button causes students to be informed about an upcoming event. The user interface stays responsive while notifications are being issued since the notification mechanism operates asynchronously on a different thread.
Fetch External Data: Pressing this button starts the process of obtaining event data from outside sources. Asynchronous data fetching simulates integration with third-party services, such as calendar or event feeds.


3. WPF Components Used:
Window and Grid: A Grid layout was used in the construction of the application's main window (MainWindow.xaml), allowing for variable UI element configuration. The header, filter section, event list, and action buttons are arranged in a grid format.

TextBlock: Used to show static text, such as the application's title and the labels containing event information.

ComboBox: Enables users to filter events by department. The filtering procedure is started by the selection change event.

ListView: Provides a table-like format for the list of events. A attribute of the event, such as name, date, type, and department, is correlated with each column.

StackPanel: Used to arrange UI components either horizontally or vertically. StackPanel is used in this application to organize the buttons, event details, and filter section.

Buttons: These offer interactive features including event registration, student notifications, and data retrieval from outside sources.

4. Functional Logic:
Event Filtering: The DepartmentFilter_SelectionChanged function is called when a department is chosen in the ComboBox. Using LINQ, this function filters the events according to the department that has been selected, updating the ListView to show only the pertinent events.

Event Selection: The EventListView_SelectionChanged function is called when a user chooses an event from the ListView. The details of the selected event are extracted by this approach and are shown in the event information section.

Notification Multithreading: The NotifyStudents_Click function uses Task to conduct the notification procedure on a different thread.Hurry. This guarantees that when notifications are being issued, the user interface stays responsive.

Asynchronous Data Fetching: The FetchEventDataAsync method is used by the FetchExternalData_Click function to start the fetching of external event data. By simulating asynchronous data retrieval, this technique enables the program to integrate with external sources without obstructing the primary user interface thread.

5. Potential Enhancements:
Styling: To improve the application's visual attractiveness, unique themes and styles can be added.
Data Persistence: The event data is hardcoded at the moment. The program can be linked to a database so that event data can be consistently stored and retrieved.
User Authentication: Provide role-based access control and user authentication so that various users (teachers, students, etc.) have varying permissions within the system.
Event Registration: Put in place a more capable system that keeps track of which users have signed up for which events.

6. How It Works:
Launch the software: A title, a list of events, and a filter option (to filter events by department) appear when the program loads.

Filter Events: The application will filter the events according to the department that users select from the ComboBox.

View Event Details: The event details section displays the details of the event that has been selected from the list.

Take Actions: By using the corresponding buttons, users can register for events, alert students, and retrieve external data.

7. User Flow:
Launch the software: Every available event is visible to the user.
Filter Events: Using the dropdown menu, the user can filter events by department.
Choose an Event: To view more information, the user chooses an event from the list.
Take Action: The user has the option to notify students, register for the event, and retrieve more information about it.
This WPF program offers a straightforward yet effective interface for organizing events on campus. It has the potential to grow into a feature-rich event management system for Monash University with more modification.

