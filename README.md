Project Aim
The aim of this project is to design and develop a User-Centric Healthcare Management Application using MIT App Inventor. This application provides a digital bridge between patients and medical services, allowing for automated doctor discovery, appointment scheduling with dynamic fee calculation based on specialist expertise, pharmacy ordering, and the maintenance of digital health records using TinyDB for local data persistence.
Technical Algorithms (10-Screen Flow)
Screen 1: Splash Screen\
Step 1:App starts and displays hospital branding/logo.
Step 2:Start a Clock Timer set to 3000ms.
Step 3: Once the timer fires, call open another screen for the LoginScreen.
Screen 2: Login / Registration
Step 1: User enters credentials (Username/Password).
Step 2 (Registration): Save user details into TinyDB using the username as the primary tag.
Step 3 (Login):Compare input password with TinyDB.GetValue for that username.
Step 4: If logic is TRUE, open Dashboard; else, trigger a Notifier alert.
Screen 3: Dash Board (Home)
Step 1:On Initialize, fetch "PatientName" from TinyDB and join with "Welcome, " in a label.
Step 2:Monitor clicks on 4 main buttons: Book Doctor, Order Meds, My Record, Profile.
Step 3:Direct the user to the corresponding Screen index based on the click.
Screen 4: Doctor Search (Departments)
Step 1:Display a ListView containing medical specialties (Cardiology, Dental, etc.).
   Step 2: When a specialty is picked, StoreValue with tag "Dept" in TinyDB.
   Step 3: Open DoctorListScreen.
   Screen 5: Doctor List
Step 1: Populate ListView with specific doctor names and their base consultation fees.
   step 2: On selection, store the entire string (e.g., "Dr. Smith ($500)") under tag "SelectedDoc".
   Step 3: Open BookingScreen.
   Screen 6: Appointment Booking
Step 1:Provide a DatePicker for the appointment date.
   Step 2: Use a TextBox to collect patient symptoms/reason for visit.
   Step 3:Store the date under tag "ApptDate" and symptoms under "Symptoms".
   Step 4: Open PaymentScreen.
Screen 7: Payment Screen (Fee Calculation)
Step 1: Fetch "SelectedDoc" from TinyDB.
   Step 2: Apply Conditional Logic:
   * If selection contains "Dr.Smith", set fee label to 500.
   * Else if selection contains "Dr.Ananya", set fee label to 1000.
   * Else, set default fee to 300.
   Step 3: On "Pay Now," store "PaidAmount" and trigger a success Notifier.
Screen 8: Digital Prescription (Summary)
Step 1: On Initialize, pull all data from TinyDB: Name, Doctor, Date, and Amount.
   Step 2: Use the join block to format these into readable labels (The "Ticket" view).
   Step 3: Generate a Random Integer for a "Reference ID."
Screen 9: Health Records (History)
Step 1: On Initialize, set a ListView's elements by joining "ApptDate", "Dept", and "SelectedDoc".
   Step 2: This allows the patient to see a persistent log of their medical history.
   Screen 10: User Profile
Step 1: Retrieve and display personal metadata (Blood Group, Age) from TinyDB.
   Step 2: Implement a Logout button that redirects back to the LoginScreen.



https://github.com/user-attachments/assets/ce44af3f-5551-470d-8f48-16bebaeb57e2


