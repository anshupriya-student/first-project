patient = {}
appointment = {}
balance = 0

# add new patient
def add_patient():
    pid = input("Enter patient id: ")
    name = input("Enter patient name: ")
    age = int(input("Enter patient age: "))
    disease = input("Enter patient disease: ")
    patient[pid] = {"name": name, "age": age, "disease": disease}
    print("Patient added successfully!\n")


# view patient details
def view_patient():
    if not patient:
        print("No patients available\n")
    else:
        for pid, details in patient.items():
            print(f"ID: {pid}, Name: {details['name']}, Age: {details['age']}, Disease: {details['disease']}")
        print("")


# book appointment
def book_appointment():
    pid = input("Enter patient id: ")
    doctor = input("Enter doctor name: ")
    time = input("Enter appointment time: ")
    appointment[pid] = {"doctor": doctor, "time": time}
    print("Appointment booked successfully!\n")


# view appointment details
def view_appointment():
    if not appointment:
        print("No appointment available\n")
    else:
        for pid, details in appointment.items():
            print(f"Patient ID: {pid}, Doctor: {details['doctor']}, Time: {details['time']}")
        print("")


# billing system
def billing():
    global balance
    room = int(input("Enter room charge: "))
    medicine = int(input("Enter medicine charge: "))
    test = int(input("Enter test charge: "))

    total = room + medicine + test
    balance += total

    print("Current bill:", total)
    print("Total hospital balance:", balance)
    print()


# main menu
while True:
    print("---- Hospital Management System ----")
    print("1. Add patient")
    print("2. View patient details")
    print("3. Book appointment")
    print("4. View appointment")
    print("5. Billing")
    print("6. Exit")

    choice = int(input("Enter your choice:"))

    if choice == 1:
        add_patient()
    elif choice == 2:
        view_patient()
    elif choice == 3:
        book_appointment()
    elif choice == 4:
        view_appointment()
    elif choice == 5:
        billing()
    elif choice == 6:
        print("Thank you! Exiting system.")
        break
    else:
        print("Invalid choice! Try again.\n")
