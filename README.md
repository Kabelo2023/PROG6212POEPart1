1. Purpose of the Application:
The goal of this application is to help Monash University track and organize various campus events. It allows users to filter events by department, view event details, and perform actions like registering for events, notifying students, and fetching data from external sources. This WPF application is designed to be user-friendly and provides a simple interface for managing campus activities.

2. Key Features:
Event Filtering: Users can filter the list of events by department (e.g., Science, Arts, Engineering). This filtering is implemented using LINQ, which allows for efficient querying and filtering of the event list based on the selected department.

Event Display: The events are displayed in a ListView control with columns for the event name, date, type, and department. The ListView provides a clean and organized way to display the list of events, making it easy for users to browse through them.

Event Details Section: When a user selects an event from the list, the details of that event (name, date, type, department) are displayed in a dedicated section on the right side of the window. This gives the user more information about the event without cluttering the main event list.

User Actions:

Register for Event: A button allows users to register for an event. Although the logic for event registration is currently simulated with a simple message box, it can be expanded to handle actual registration processes.
Notify Students: This button triggers the notification of students about an event. The notification process runs asynchronously in a separate thread, ensuring that the UI remains responsive while notifications are being sent.
Fetch External Data: This button initiates the fetching of event data from external sources. The data fetching is done asynchronously, simulating integration with external services like event feeds or calendar services.

3. WPF Components Used:
Window and Grid: The main window of the application (MainWindow.xaml) is built using a Grid layout, which allows for flexible arrangement of UI elements. The grid organizes the title, filter section, event list, and action buttons.

TextBlock: Used for displaying static text, such as the title of the application and the labels for event details.

ComboBox: Allows users to select a department for filtering events. The selection change event triggers the filtering process.

ListView: Displays the list of events in a table-like format. Each column corresponds to a property of the event, such as name, date, type, and department.

StackPanel: Used to group UI elements vertically or horizontally. In this application, StackPanel is used for arranging the filter section, event details, and buttons.

Buttons: These provide interactive functionality, such as registering for events, notifying students, and fetching external data.

4. Functional Logic:
Event Filtering: When a department is selected in the ComboBox, the DepartmentFilter_SelectionChanged method is called. This method filters the events based on the selected department using LINQ and updates the ListView to display only the relevant events.

Event Selection: When a user selects an event from the ListView, the EventListView_SelectionChanged method is triggered. This method extracts the selected event's details and displays them in the event details section.

Multithreading for Notifications: The NotifyStudents_Click method runs the notification process on a separate thread using Task.Run. This ensures that the UI remains responsive while notifications are being sent.

Asynchronous Data Fetching: The FetchExternalData_Click method initiates the fetching of external event data using the FetchEventDataAsync method. This method simulates retrieving data asynchronously, allowing the application to integrate with external sources without blocking the main UI thread.

5. Potential Enhancements:
Styling: The application can be enhanced with custom styles and themes to make the UI more visually appealing.
Data Persistence: Currently, the event data is hardcoded. You can connect the application to a database to store and retrieve event data persistently.
User Authentication: Add user authentication and role-based access control, so different users (e.g., students, faculty) have different permissions within the system.
Event Registration: Implement a more robust registration system that tracks which users have registered for which events.

6. How It Works:
Start the Application: The application loads with a title, a filter option (to filter events by department), and a list of events.

Filter Events: Users can select a department from the ComboBox, and the application will filter the events based on the selection.

View Event Details: When an event is selected from the list, its details are shown in the event details section.

Perform Actions: Users can register for events, notify students, and fetch external data using the respective buttons.

7. User Flow:
Open the Application: The user sees all available events.
Filter Events: The user can filter events by department using the dropdown menu.
Select an Event: The user selects an event from the list to see more details.
Take Action: The user can register for the event, notify students, or fetch additional data about events.
This WPF application provides a simple but powerful interface for managing campus events. With further customization and additional features, it can become a comprehensive event management system for Monash University.
