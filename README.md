# autoupdatesheet.py
import csv ### importing CSV files

def write_into_csv(info_list):
    with open ("students_information.csv", mode = 'a') as file:
        writer = csv.writer(file)### to add the information to file only once if the sheet or file is zero that means no data is present
        if file.tell() == 0:
            writer.writerow(["Name","Age","Phone number","Place","E-mail"])### adding the list in the excel sheet 
        writer.writerow (info_list)


if __name__ =='__main__':
 ### taking intially condition as true
 condition = True
 student_num = 1



 while(condition):


### taking input from the user 
    student_info = input("Enter your student information for student #{} in order of name, age, phone number, place, email: ".format(student_num))
  


### converting the input in list  
    student_info_list = student_info.split(",")
 

    print("\nthe entered information is -\nName:{}\nAge:{} \nPhone number:{} \nPlace:{} \nEmail:{}".format(student_info_list[0],student_info_list[1],student_info_list[2],student_info_list[3],student_info_list[4]))

    choice_check=input("Is the entered information is correct? (yes/no): ")


    if choice_check == "yes":
         write_into_csv(student_info_list)### calling the function
         condition_check = input("Enter (yes/no) if you want to add any students information")
         if condition_check == "yes":
              condition = True
              student_num = student_num +1
         else:
              condition= False
    elif choice_check =="no":
        print("\nplease re-enter the values!!!")

