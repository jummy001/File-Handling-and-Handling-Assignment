# File-Handling-and-Handling-Assignment

def modify_text(content):
    # Example modification: convert to uppercase and add line numbers
    lines = content.splitlines()
    modified_lines = [f"{idx + 1}: {line.upper()}" for idx, line in enumerate(lines)]
    return "\n".join(modified_lines)

try:
    # Ask the user for a filename
    filename = input("Enter the name of the file to read: ")

    # Attempt to open and read the file
    with open(filename, "r") as infile:
        content = infile.read()

    # Modify the content
    modified_content = modify_text(content)

    # Write to a new file
    with open("modified_output.txt", "w") as outfile:
        outfile.write(modified_content)

    print("✅ modified_output.txt has been created with the modified content.")

except FileNotFoundError:
    print("❌ Error: The file does not exist.")
except IOError:
    print("❌ Error: The file could not be read.")
except Exception as e:
    print(f"❌ Unexpected error: {e}")
