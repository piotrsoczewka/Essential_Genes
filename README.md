## 1) Introduction

Before we begine, I would like to point out that this project is expected to be browsered not only by biologists, but also by people without relevant background. Therefore, below text is full of simplifications of which I am aware, yet I hope the basics of genetics are adequately explained. So, without further ado, let's start.

Every living organism contains instructions allowing development and functioning of an individual. These instructions are encoded in DNA - a long, chain-like molecule consisting of two strands which forms a famous double helix structure. Each strand is a string of four different elements called bases. They are adenine (A), thymine (T), cytosine (C) and guanine (G) and order of these bases determines information about a living organism. Both strands in DNA molecule are complementary - a each base from one strand interacts with a respective base from the other strand. A interacts with T, and C interacts with G, and vice versa. If you are a programmer, let's take a look on the below create_complementary_strand function converting a DNA strand into its complementing strand to understand this better:

    def create_complementary_strand(your_strand):
        '''Creates a complementary DNA strand to given DNA strand.'''

        # making sure the given sequence will be suitable for conversion
        your_strand = your_strand.replace(' ', '').upper()

        complementation_pattern = {
            'A' : 'T',
            'T' : 'A',
            'C' : 'G',
            'G' : 'C'
        }

        complementary_strand = ''

        for base in your_strand:
            try:
                complementary_strand = (complementary_strand + complementation_pattern[base])
            except KeyError:
                print('Error - an invalid bases was in given in the original DNA strand')
                print('Can not create a complementary_strand')
                complementary_strand = False
                break

        return complementary_strand
   
And here a simple example to ilustrate this function:


Hopefully now this is more understandable.

To put it simply, the order of these bases in DNA determines information about a living organism. 

4 different components called bases: adenine (A), thymine (T), cytosine (C) and guanine (G). These 4 bases form a strand with unique bases composition. Each strand is accompanied

## 2) Tools used in the project
* Python
* Pandas
* Seaborn
* Statistics (significance testing, pingouin and scikit_posthocs libraries)

## 3) Data colletion
