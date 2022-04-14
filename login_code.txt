from string import whitespace
from tkinter import *
from PIL import ImageTk
from tkinter import messagebox


class login:
    def __init__(self, root):
        self.root = root
        self.root.title("Embot")
        self.root.geometry("1080x615+100+50")
        self.root.resizable(False, False)

        # background image.
        self.bg = ImageTk.PhotoImage(
            file="C:\\Users\HP\\OneDrive\\Desktop\\Email-bot's\\login.jpg")
        self.bg_image = Label(self.root, image=self.bg).place(
            x=0, y=0, relwidth=1, relheight=1)

        # login frame
        Frame_login = Frame(self.root, bg="white")
        Frame_login.place(x=50, y=120, width=500, height=400)

        #title and subtitle

        title = Label(Frame_login, text="Email - Bot", font=(
            "Century", 35, "bold"), fg="coral", bg="ghost white").place(x=110, y=40)
        subtitle = Label(Frame_login, text="Login to Email - Bot", font=(
            "Goudy old style", 14), fg="black", bg="ghost white").place(x=150, y=115)

        # Username
        lbl_user = Label(Frame_login, text="Username", font=(
            "Century", 13), fg="black", bg="ghost white").place(x=50, y=170)
        self.username = Entry(Frame_login, font=(
            "Century", 13), bg="#E7E6E6")
        self.username.place(x=50, y=200, width=320, height=35)

        # Password
        lbl_password = Label(Frame_login, text="Password", font=(
            "Century", 13), fg="black", bg="ghost white").place(x=50, y=250)
        self.password = Entry(Frame_login, font=(
            "Century", 13), bg="#E7E6E6")
        self.password.place(x=50, y=280, width=320, height=35)

        # Submit Button
        # forget = Button(Frame_login, text="Forget Password", font=(
        # "Goudy old style", 15, "bold"), fg="black", bg="seashell2").place(x=50, y=340)

        Submit = Button(Frame_login,command=self.check_func, cursor="hand2", text="Login?", bd=0.5, font=(
            "Century", 13), fg="black", bg="white smoke").place(x=160, y=340, width=150, height=35)

    def check_func(self):
        if self.username.get() == "" or self.password.get() == "":
            messagebox.showerror(
                "Error", "Please Enter Username & Password", parent=self.root)
        elif self.username.get() != "yash123" or self.password.get() != "12345678":
            messagebox.showerror(
                "Error", "Invalid Username or Password", parent=self.root)
        else:
            messagebox.showinfo("Welcome", f"Welcome{self.username.get()}")


root = Tk()
obj = login(root)
root.mainloop()
