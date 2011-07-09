---
title: Sequence Cleaner
permalink: wiki/Sequence_Cleaner
layout: wiki
tags:
 - Cookbook
---

Description
-----------

I want to share my script using biopython to clean sequences up , you
should know analyzing poor data takes CPU time and interpreting the
results from poor data takes people time, so it's always important to
make a preprocessing.

Let me call my script as “Sequence\_cleaner” and the big idea is to
remove duplicate sequences, remove too short sequences ( the user
defines the minimum length) and remove sequences which have too many
unknown nucleotides (N) ( the user defines the % of N is allows ) and in
the end the user can choose if he/she wants to have a file as output or
print the result.

Script
------

``` python
from Bio import SeqIO
 
def sequence_cleaner(fasta_file,min_length=0,por_n=100):
    #create our hash table to add the sequences
    sequences={}

    #Using the biopython fasta parse we can read our fasta input
    for seq_record in SeqIO.parse(fasta_file, "fasta"):
        #Take the current sequence
        sequence=str(seq_record.seq).upper()
        #Check if the current sequence is according to the user parameters
        if (len(sequence)>=min_length and (float(sequence.count("N"))/float(len(sequence)))*100<=por_n):
       # If the sequence passed in the test "is It clean?" and It isnt in the hash table , the sequence and Its id are going to be in the hash
            if sequence not in sequences:
                sequences[sequence]=seq_record.id
       #If It is already in the hash table, We're just gonna concatenate the ID of the current sequence to another one that is already in the hash table
            else:
                sequences[sequence]+="_"+seq_record.id

            
    #Write the clean sequences
                
    #Create a file in the same directory where you ran this script
    output_file=open("clear_"+fasta_file,"w+")
    #Just Read the Hash Table and write on the file as a fasta format
    for sequence in sequences:
            output_file.write(">"+sequences[sequence]+"\n"+sequence+"\n")
    output_file.close()



#sequence_cleaner("Aip_coral.fasta",10,10)

"You should call the function 'sequence_cleaner', there are 3 basic parameters:
"                    #1st: your fasta file 
"                    #2nd: the user defines the minimum length (default value 0 ( It means you don't have to care about the minimum lenght)
"                    #3rd: the user defines the % of N is allowed (default value 100 ( It means  you dont care to 'N' in your sequences))
"FYI if you don't care about the 2nd and the 3rd parameters you are just gonna remove the duplicate sequences"
```

Questions
---------

Any question send an email to: genivaldo.gueiros@gmail.com