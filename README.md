tasks = []
file = open("tasks.txt", "r")
for line in file:
    tasks.append(line.strip())
file.close()

while True:
    print("\n1. Add Task")
    print("2. View Task")
    print("3. Delete Task")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if(choice == "1"):
        task = input("Enter the task: ")
        tasks.append(task)
        print("Task added!")
    elif(choice == "2"):
        print("\nYour Tasks: ")
        for i, task in enumerate(tasks):
            print(i + 1, ".", task)
    elif(choice == "3"):
        num = int(input("Enter task number to delete: "))
        tasks.pop(num - 1)
        print("Task Deleted!")
    elif(choice == "4"):
        print("Goodbye!")
        break
    else:
        print("Invalid choice")

file = open("tasks.txt", "w")
for task in tasks:
    file.write(task + "\n")
file.close()
    
