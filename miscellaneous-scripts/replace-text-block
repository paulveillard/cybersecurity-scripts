#!/bin/python

# This script replaces text in a file. The search text and replacement text 
# are in two other, separate files.

import os
import sys

import argparse

parser=argparse.ArgumentParser(
    description='''Searches through a text file for a block of text and replaces it with another text block.''')
parser.add_argument('change_file', help='File to be changed')
parser.add_argument('search_text_file', help='File that contains the text to search for')
parser.add_argument('replacement_text_file', help='File that contains the new (replacement) text')
args=parser.parse_args()


# Read in the search text
with open(args.search_text_file, 'r') as search_text_file :
  search = search_text_file.read()

# Read in the replacement text
with open(args.replacement_text_file, 'r') as replacement_text_file :
  replacement = replacement_text_file.read()

# Read in the file to be changed
with open(args.change_file, 'r') as change_file :
  filedata = change_file.read()

# Replace the target string (only first occurrence)
newfiledata = filedata.replace(search, replacement, 1)

if newfiledata == filedata :
  print("File not changed: " + str(args.change_file));
  sys.exit(1);

# Write the file out again
with open(args.change_file, 'w') as change_file:
  change_file.write(newfiledata)
