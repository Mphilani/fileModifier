# fileModifier
def modify_content(content):
    """Modify the file content (example: convert text to uppercase)."""
    return content.upper()  

def process_file():
    
    filename = input("Enter the filename to read: ")
    
    try:
        
        with open(filename, "r") as file:
            content = file.read()
        
        
        modified_content = modify_content(content)
        
        
        new_filename = "modified_" + filename
        with open(new_filename, "w") as new_file:
            new_file.write(modified_content)
        
        print(f"Modified content saved in {new_filename} 🎉")
    
    except FileNotFoundError:
        print(" Error: The file does not exist. Please check the filename and try again.")
    except PermissionError:
        print(" Error: Permission denied. You might not have access to this file.")
    except Exception as e:
        print(f" An unexpected error occurred: {e}")


process_file()
