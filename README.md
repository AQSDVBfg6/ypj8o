ypj8o

print("""
██╗   ██╗██████╗      ██╗ ██████╗  ██████╗ 
╚██╗ ██╔╝██╔══██╗     ██║██╔═══██╗██╔═══██╗
 ╚████╔╝ ██████╔╝     ██║██║   ██║██║   ██║
  ╚██╔╝  ██╔═══╝ ██   ██║██║   ██║██║   ██║
   ██║   ██║     ╚█████╔╝╚██████╔╝╚██████╔╝
   ╚═╝   ╚═╝      ╚════╝  ╚═════╝  ╚═════╝ 
              Y P J 8 O
""")

import re

def check_password(password):
    score = 0

    # الطول
    if len(password) >= 8:
        score += 1
    if len(password) >= 12:
        score += 1

    # حروف صغيرة وكبيرة
    if re.search(r"[a-z]", password):
        score += 1
    if re.search(r"[A-Z]", password):
        score += 1

    # أرقام
    if re.search(r"[0-9]", password):
        score += 1

    # رموز خاصة
    if re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        score += 2

    # تقييم النتيجة
    print("\n----------------------")
    print("🔐 Password Analysis")
    print("----------------------")

    if score <= 2:
        print("❌ Weak Password")
        print("⚠️ Recommendation: Use more characters, numbers and symbols.")

    elif score <= 4:
        print("⚠️ Medium Password")
        print("💡 Try adding special characters and increasing length.")

    elif score <= 6:
        print("💪 Strong Password")
        print("✔ Good job, but can still be improved.")

    else:
        print("🔥 Very Strong Password")
        print("✔ Excellent security level!")

    print("----------------------\n")


def main():
    print("🔐 Password Strength Checker Tool")
    print("Type 'exit' to quit\n")

    while True:
        pwd = input("Enter password: ")

        if pwd.lower() == "exit":
            print("Bye 👋")
            break

        check_password(pwd)


if __name__ == "__main__":
    main()
    
