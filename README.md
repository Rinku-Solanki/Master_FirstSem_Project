# Master_FirstSem_Project
Project Tittle:
Create a python program that allows user to manage tasks: track the time spend on them,and mark as done,or not done
1)A task has a name,a status(True/False) and a duration in hours
2)Data will be stored as a 3 lists:task name,task satus,task duration
3)the program will run atleast 200 times untill user type Exit to stop running program
4)Operation to be preform: add task,Display all products/task, remove task,edit task,search task,mark as a done,Help

How to the run the project : according the requirement just simple run display all the details as default
Next: write the task name what you want to add and same way write the task name what you want to delete,it will display all the details of task /status/hours
this process will continue untill 200 times/you can add/delete task 200 times untill you enter Exit,program stop and out of the loop

Developed by: Rinku Aniruddh Parmar (Matriculation No:401060366)
Course : M.Sc.(Computer Science):1st Semester
Subject: Introduction to Python Programming(Id: M01_04.2)(Code: M-IEIM M 1.4.2)
Prof. :  Miss. Ghazal Nazari(Experienced Professor)          
task=[]
status=[]
duration=[]
print(task) #list to store the tasks name
print(status)#task status
print(duration)#task duration in hours
  
task.append("cooking") #adding task to list
task.append("cleaning")
task.append("reading")
task.append("writing")

status.append(False) #initial status of tasks
status.append(False)
status.append(False)
status.append(False)

duration.append(None) #initial duration of tasks
duration.append(None)
duration.append(None)
duration.append(None)

print("Initial tasks:", task)
print("Initial statuses:", status)
print("Initial durations:", duration)

print("\nType 'exit' at any input to stop the program.\n")

# Repeat maximum 200 times
for a in range(200):

    print("Steps number:",a + 1)

    # ADD TASK
    add_task = input("Enter the new task: ")

    if add_task.lower() == "exit":
        print("Program exited by user.")
        break

    if add_task in task:
        print("Task is already in list")
    else:
        task.append(add_task)
        status.append(False)
        duration.append(None)

    print("All Tasks:")
    print("updated task after  new task added:", task)
    print("Updated status after status added:", status)
    print("Updated durations after duration added:", duration)

    #search task in list
    search_task = "reading" #manually search any task in list

    if search_task in task:
        i = task.index(search_task)
        print("Search task details:")
        print("All the details of search_task:",search_task)
        print(task[i])
        print(status[i])
        print(duration[i])
    else:
        print("task is not in the list")

    #Edit the task/status/duration  
    task[2]="shopping" #maually edit task at the 2 index point:it will put to the index 2 with the task shopping/status:True/Duration:5 hours
    status[1]=True
    duration[3]=5
    print("All Tasks:")
    print("Updated tasks after task edited:", task)
    print("Updated status after status edited:", status)
    print("Updated durations after duration edited:", duration)

    #Task we want to mark as done
    task_done = "reading"  

    if task_done.lower() == "exit":
        print("Program exited by user.")
        break

    if task_done in task:
        j = task.index(task_done) 
        start_hour = 10
        end_hour=12
        hours_taken=end_hour - start_hour
        status[j] = True
        duration[j] = hours_taken
        print("marked as a task done")
        print("Time taken in hours:",hours_taken)
    else:
        print("Task not found")

    print("After marking done:")
    print("Tasks:", task)
    print("Status:", status)
    print("duration:", duration)

    #user remove the  task name/status/duration
    remove_task=input("Enter the remove task name")

    if remove_task.lower() == "exit":
        print("Program exited by user.")
        break

    if remove_task in task:
        index = task.index(remove_task)
        task.pop(index)
        status.pop(index)
        duration.pop(index)
        print("removed task successfully")
    else:
        print("task is not available in list ")

    print("All Tasks:")
    print("Updated tasks after task  removed:", task)
    print("Updated status after status removed:", status)
    print("Updated durations after duration removed:", duration)

    # Display Details
    total_tasks = len(task)
    completed_tasks = status.count(True)
    uncompleted_tasks = status.count(False)

    total_hours = 0
    for d in duration:
        if d is not None:
            total_hours = total_hours+d

    print("Total number of tasks:", total_tasks)
    print("Completed tasks:", completed_tasks)
    print("Uncompleted tasks:", uncompleted_tasks)
    print("Total hours worked:", total_hours)

    #Display help message
    print("--- HELP MENU ---")
    print("1. Add Task      : Adds a new task with default status False and duration None.")
    print("2. Remove Task   : Removes a task using its name.")
    print("3. Edit Task     : Updates task name, status, or duration manually in code.")
    print("4. Search Task   : Searches a task and displays its details.")
    print("5. Mark Task Done: Marks a task as completed and show its status and hours worked")
    print("6. Display Tasks : Shows all tasks with status and duration.")
    print("7. Display Details:\nTotal number of tasks,\nNumber of completed tasks,\nNumber of uncompleted tasks,\nTotal hours worked")
    print("8. Help          : Displays this help message.")

  
else:
    print("\nMaximum 200 steps reached. Program stopped.")
