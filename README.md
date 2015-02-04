# homework-wk-5-1
homework 2/3/15
<<<<<<< HEAD
#processing DNA in a file
file = open("dnastrand.txt")
for dna in file:
    print(dna)
#remove the first 14 bases of the sequences but dont write and end because all the sequences are a different length.
file = open("dnastrand.txt")
for dna in file:
    trimmed_dna = dna[14:]
    print(trimmed_dna)
#now we are going to write this to a file
#open the input file
file = open("dnastrand.txt")
#open the output file
output = open("trimmed.txt", "w")
#go through the input file one line at a time
for dna in file:
    trimmed_dna = dna[14:]
    output.write(trimmed_dna)
    print("processed sequence with length" + str(len(trimmed_dna)))


#exercise exons from genomic DNA
exon_locations = open("exons.txt")
for line in exon_locations:
    print(line)
#all we've done is open the file and print the lines to the screen which gives us a loop with a different exon each time around.
#now split up each line into a start and stop position
exon_locations = open("exons.txt")
for line in exon_locations:
    positions = line.split(',')
    print(positions)
#the lines become lists of two elements, now assign start and stop positions to variable names and print them out individually
exon_locations = open("exons.txt")
for line in exon_locations:
    positions = line.split(',')
    start = positions[0]
    stop = positions[1]
    print("start is " + start + ", stop is " + stop)
#now read the genomic file and use the exon coordinates to extract the one exon at a time and print it to the screen.
genomic_dna = open("genomic_dna.txt").read()
exon_locations = open("exons.txt")
for line in exon_locations:
    positions = line.split(',')
    start = int(positions[0])
    stop = int(positions[1])
    exon = genomic_dna[start:stop]
    print("exon is: " + exon)
#we used int() because when we use split we get strings therefore the start and stop variables are strings but we need to use them as numbers so in order to turn the strings to numbers use the int()
#now to concatenate the exon sequence to make a long coding sequence we will create a new variable and assign it to an empty string and then each time round the loop you ad the current exon to the end and store the result back in the same variable.
genomic_dna = open("genomic_dna.txt").read()
exon_locations = open("exons.txt")
coding_sequence = ""
for line in exon_locations:
    positions = line.split(',')
    start = int(positions[0])
    stop = int(positions[1])
    exon = genomic_dna[start:stop]
    coding_sequence = coding_sequence + exon
    print("coding sequence is : " + coding_sequence)
#now we got to save this coding sequence to a file rather than print it to the screen
#open the genomic_dna file and read the contents
genomic_dna = open("genomic_dna.txt").read()
#open the exon locations file
exon_locations = open("exons.txt")
#creates a variable to hold the actual coding sequence
coding_sequence = ""
#goes through each line in the exon locations file
for line in exon_locations:
#split the line using a comma
    positions = line.split(',')
#get the start and stop positions
    start = int(positions[0])
    stop = int(positions[1])
#extract the exons from the genomic dna
    exon = genomic_dna[start:stop]
#append the exon to the end of the current coding sequence
    coding_sequence = coding_sequence + exon
    #write the coding sequence to an output file
    output = open("coding_sequence.txt", "w")
    output.write(coding_sequence)
    output.close()
=======
>>>>>>> origin

