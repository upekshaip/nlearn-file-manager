# nlearn-file-manager v3

- This is a tool to auto download every file from Nlearn to local computer
- This is the gui version vr3.05


<br>

## Issues found in recently:
- there is a issue with the names of files, sections and topic names. because of that sometimes the application did not worked.
    - some files have "\t" or "\n" characters
    - " " character found in file section
    - also find "?" in the section names
```py
if file_type == "File":
    file_name = file_name.replace('/', ' or')
    file_name = file_name.replace('/n', ' - ')
    file_name = file_name.replace('/t', ' - ')
    file_name = file_name.replace('?', ' - ')
    file_data = {"file_name": file_name, "ext": ext, "url": url,"type": file_type}
```

- they added some new file types aswell. Some of the main files are now fixed. But still not downloading the every file.
- I added the bellow line to the show_table method. So all the unknown files have .unknown exetension. Also every unknown file is ignored.
```py 
ext = "unknown"
if "text" in type_of_file_url:
    ext = "txt"
```
- Found a .mpeg file in plymouth group. It also added to the ignored extension list.
```py 
if "mpeg" in type_of_file_url:
    ext = "mpeg"
```
- Also added "ignore_course.json" file to ignore the unnessassary courses.
- Added "dev.json" file to bypass the login section. It directly scan the web moodle session.
----------

- fixed some of issues in v3.01 and again appier the issues. So that's why I released the v3.05

<br>
Solely coded by upekshaip
