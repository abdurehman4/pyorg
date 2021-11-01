#! /usr/bin/python3
# For dealing with files
import os
from termcolor import cprint


# Yes or not
yesno = str()

# List of files and folders in current directory
folders_and_files = os.listdir()


# Extensions Lists
files = []
pics_ext = ['.png','.jpg','.jpeg','.webp','.svg']
video_ext = ['.mpv','.mp4','.avi']
audio_ext = ['.mp3']
docs_ext = ['.doc','.docx','.pdf','.txt','.xls','.xlsx','.ppt','.pptx']
programming_ext = ['.c','.cpp','.py','.js','.java']
compressed_ext = ['.zip','.7z','.tar']



# Files Lists
compressed = []
pics = []
videos = []
audios = []
docs = []
programming = []
others = []




# Files and their Folder

files_folder = [
    [pics,"Pictures"],
    [videos,"Videos"],
    [audios,"Audios"],
    [docs,"Documents"],
    [programming,"Programming"],
    [compressed,"Compressed"],
    [others,"Others"]
]


# Functions
def createFolderIfNotExists(folder_name):
    if not os.path.exists(folder_name):
        os.mkdir(folder_name)


def extCheckAndAppend(file,exts,list_to_append):
    for ext in exts:
        if ext in file:
            list_to_append.append(file)
        else : pass



def otherFilesAppend(file):
    if  (file not in pics) and (file not in videos) and (file not in audios) and (file not in docs) and (file not in programming) and (file not in compressed):
        others.append(file)




def moveAllFilesToFolder(files,folder):
    for file in files:
        os.rename(file,os.path.join(folder,file))


def runFuncIfNotEmpty(files,folder):
    if len(files) != 0:
        createFolderIfNotExists(folder)
        moveAllFilesToFolder(files,folder)

# Adding only files to the files list
for file_or_folder in folders_and_files:
    if os.path.isfile(file_or_folder):
        files.append(file_or_folder)
    else : pass


if len(files) == 0:
    cprint("There is nothing to do!",'red')
    exit()


# Adding Files to list
for file in files:
    extCheckAndAppend(file,pics_ext,pics)
    extCheckAndAppend(file,video_ext,videos)
    extCheckAndAppend(file,audio_ext,audios)
    extCheckAndAppend(file,docs_ext,docs)
    extCheckAndAppend(file,programming_ext,programming)
    extCheckAndAppend(file,compressed_ext,compressed)
    otherFilesAppend(file)


# Moving files and creating folders
def organize():
    for file_folder in files_folder:
        runFuncIfNotEmpty(file_folder[0],file_folder[1])



# Prints the information
files_info = "Number of Files: " + str(len(files))

cprint (files_info,'green')

cprint("Files:\n",'cyan')
cprint(files,'cyan')
cprint("\n",'cyan')


for file_folder in files_folder:
    cprint (file_folder[1]+str("\n"),'cyan')
    cprint (file_folder[0],'cyan')
    cprint("\n",'cyan')

yesno = str(input("Organize ? [Y/n] :")).lower()

if yesno == "y":
    organize()
    print("Successfully Organized!")
else :
    cprint("Aborted\n" , 'red')
