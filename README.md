# assignmentpython4

def modify_content(content):
   
    return content.upper()

def main():
    filename = input("Enter the filename to read from: ")

    try:
        with open(filename, "r") as infile:
            content = infile.read()
            print("Original content read successfully.")

        modified_content = modify_content(content)

        new_filename = "modified_" + filename
        with open(new_filename, "w") as outfile:
            outfile.write(modified_content)
            print(f"Modified content written to '{new_filename}'.")

    except FileNotFoundError:
        print(f" Error: The file '{filename}' was not found.")
    except IOError:
        print(f" Error: Could not read or write file.")

if __name__ == "__main__":
    main()
