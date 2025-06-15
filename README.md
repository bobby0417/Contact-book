# Contact-book 
contacts = {}

def add_contact():
    name = input("Enter name: ")
    phone = input("Enter phone number: ")
    email = input("Enter email: ")
    address = input("Enter address: ")
    contacts[name] = {"Phone": phone, "Email": email, "Address": address}
    print("Contact added successfully.")

def view_contacts():
    if not contacts:
        print("No contacts available.")
        return
    for name, details in contacts.items():
        print(f"\nName: {name}")
        for key, value in details.items():
            print(f"{key}: {value}")

def search_contact():
    search_name = input("Enter name to search: ")
    if search_name in contacts:
        print(f"Details for {search_name}: {contacts[search_name]}")
    else:
        print("Contact not found.")

def update_contact():
    name = input("Enter the contact name to update: ")
    if name in contacts:
        phone = input("Enter new phone: ")
        email = input("Enter new email: ")
        address = input("Enter new address: ")
        contacts[name] = {"Phone": phone, "Email": email, "Address": address}
        print("Contact updated.")
    else:
        print("Contact not found.")

def delete_contact():
    name = input("Enter the contact name to delete: ")
    if name in contacts:
        del contacts[name]
        print("Contact deleted.")
    else:
        print("Contact not found.")

def main():
    while True:
        print("\nContact Book Options:\n1. Add\n2. View\n3. Search\n4. Update\n5. Delete\n6. Exit")
        choice = input("Choose an option (1-6): ")
        if choice == "1":
            add_contact()
        elif choice == "2":
            view_contacts()
        elif choice == "3":
            search_contact()
        elif choice == "4":
            update_contact()
        elif choice == "5":
            delete_contact()
        elif choice == "6":
            break
        else:
            print("Invalid choice. Try again.")

main()
