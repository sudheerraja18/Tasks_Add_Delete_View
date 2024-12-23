
import json

tasks_list = []

def show_menu_adv():
    print("\n--- To-Do List Menu ---")
    print("1. Add a task")
    print("2. View all tasks")
    print("3. Mark a task as completed")
    print("4. Delete a task")
    print("5. Save tasks")
    print("6. Exit")
    choice = input("Enter your choice: ")
    return choice


def load_tasks(json_file="developing.json"):
    try:
        with open(json_file, 'r') as file:
            data = json.load(file)
    except FileNotFoundError:
        data = []
    return data

def save_tasks(tasks, json_file="developing.json"):
    with open(json_file, 'w') as file:
        json.dump(tasks, file)

def add_task(tasks_list):
    task = input("Enter the new task tobe added : ")  
    for item in tasks_list:
        if task == item['task']:
            print (f"Task {task} already added...")
            return 0
    tasks_list.append({"task":task, "completed":False})
    print(f"Task '{task}' added.")
    print (tasks_list)

def view_tasks(tasks_list):
    for i, task in enumerate(tasks_list):
        status = 'Done' if task['completed'] else 'Not Done'
        res = str(i+1)+ ". " + str(task['task']) + " " + "[" + status + "]"
        print (f"{res}")

def mark_tasks_as_completed(tasks_list, json_file="developing.json"):
    view_tasks(tasks_list)
    choice = int(input("Enter your choice: "))
    if 0 < choice <= len(tasks_list):
        tasks_list[choice-1]['completed'] = 'True'
        with open(json_file, 'w') as file:
            json.dump(tasks_list, file)
    else:
        print ("Invalid Task .....")

def delete_task(tasks_list, json_file="developing.json"):
    del_iter = input("Enter the item to delete: ")
    for item in tasks_list:
        if del_iter == item['task']:
            tasks_list.remove(item)
    with open(json_file, 'w') as file:
            json.dump(tasks_list, file)
        
def main():

    tasks_list = load_tasks()

    while True:
        choice = show_menu_adv()
        if choice == '1':
            add_task(tasks_list)
        elif choice == '2':
            view_tasks(tasks_list)
        elif choice == '3':
            mark_tasks_as_completed(tasks_list)
        elif choice == '4':
            delete_task(tasks_list)
        elif choice == '5':
            save_tasks(tasks_list)
        elif choice == '6':
            save_tasks(tasks_list)
            break

if __name__ == "__main__":
    main()
