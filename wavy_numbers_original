import os
import time
import platform

current_os = platform.system()


def clear_terminal():

    if current_os == "linux" or current_os == "linux2": # LINUX
        operating_system = "Linux"
        os.system("clear")

    elif current_os == "darwin": # APPLE / MAC
        operating_system = "macOS"
        os.system("clear")

    elif current_os == "win32": # WINDOWS
        operating_system = "Windows"
        os.system("cls")

    else:
        operating_system = r"an ~undefined~ operating system"
        os.system("cls")

    return operating_system


def get_terminal_size():
    if current_os in ["linux", "linux2", "darwin", "Darwin"] or current_os.startswith("CYGWIN"): # LINUX and MAC
        rows, columns = os.popen('stty size', 'r').read().split()

    elif current_os in ["win32", "Windows"]: # WINDOWS
        columns, rows = os.get_terminal_size()

    else:
        columns, rows = os.get_terminal_size()

    return columns


def wait():
    #time.sleep(0.000020) #slowed down
    time.sleep(0.0000000000020)
    #time.sleep(0) #instant calculation

def print_block_characters(i):
    while True:
        stopper = get_terminal_size()

        while len(str(i)) < stopper:
            stopper = get_terminal_size()

            if len(str(i)) == stopper or len(str(i)) > stopper:
                break

            else:
                wait()
                block = "█" * int(len(str(i)))
                print(str(block))
                i = i * 2

        while i > 2:
            stopper = get_terminal_size()

            if i == 0 or i < 2:
                break

            else:
                wait()
                block = "█" * int(len(str(i)))
                print(str(block))
                i = i // 2


def print_numbers(i):
    while True:
        stopper = get_terminal_size()

        while len(str(i)) < stopper:
            stopper = get_terminal_size()

            if len(str(i)) == stopper or len(str(i)) > stopper:
                break

            else:
                wait()
                print(i)
                i = i * 2

        while i > 2:
            stopper = get_terminal_size()

            if i == 0 or i < 2:
                break

            else:
                wait()
                print(i)
                i = i // 2


operating_system = clear_terminal()

columns = get_terminal_size()


print(f"<<<<< You are currently running this program on {operating_system}. >>>>>\n")

print("""
Select the type of waves to be printed.

blocks == print blocks
numbers == print numbers
""")

user_select = input("Please input 'blocks' or 'numbers' to continue: ")

i = 2

while user_select.lower() != "quit" or user_select != "":

    if user_select.lower() == "blocks":
        print_block_characters(i)

    elif user_select.lower() == "numbers":
        print_numbers(i)

    user_select = input("Please input either 'blocks' or 'numbers' to continue: ")
