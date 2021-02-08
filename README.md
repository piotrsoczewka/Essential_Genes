## 1) Theoretical introduction

Welcome to my project, in which I am going to analyse some yeast genomic data and try to build some machine learning models to predicts some of the genes' features. However, because it could be browsered not only by biologists, but also by people without relevant background, I provide below a short explanation of genetics fundamentals. Many simplifications have been done, yet I hope the basics of genetics relevant for this project are adequately explained. So, without further ado, let's start.

Every living organism contains instructions allowing development and functioning of an individual. These instructions are encoded in DNA - a long, chain-like molecule consisting of two strands which forms a famous double helix structure. Each strand is a string of four different elements called bases. They are adenine (A), thymine (T), cytosine (C) and guanine (G) and order of these bases determines information about a living organism. Both strands in DNA molecule are complementary - a each base from one strand interacts with a respective base from the other strand. A interacts with T, and C interacts with G, and vice versa. I think that the below image explains it enough, but to have a full picture, I wrote also the create_complementary_strand function converting a DNA strand into its complementing strand. By playing a bit with it, I think the idea behind creating complementary DNA strands should be clear.


    def create_complementary_strand(your_strand):
        '''Creates a complementary DNA strand to given DNA strand.'''

        # Making sure the given sequence format will be suitable for conversion.
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

Before we jump into data analysis and model building, a few more theoretical notes:

* while bases sequence determines a living organisms features, it also determines DNA physico-chemical properties: G and C interaction between two strands is stronger than A and T interaction. This means that the more C and G a DNA molecule have, the more energy is required for strands separation to overcome interactions between complementary bases.
    
* organisms  have several DNA molecules in each cell. For example, humans have 46 separate DNA molecules, 23 from each parent. Each of this molecule forms a chromosome - this characteristic X shape structure which is a condensed DNA form. One can also find other DNA molecules in living cells, such as mitochondrial chromosome. Yes, the powerplant of the cell has their own DNA!
    
* instructions encoded in DNA are not located on the whole DNA molecule but in fragments called genes. The analogy here could be a file saved on a hard-drive - like a file takes only some of the available space on a hardrive, a gene takes only a fragment of the whole DNA strand of a particular sequence. Like a file has its onw size, a gene has its own length.

I hope that this short introduction would be helpful to understand what I present in this project.

## 2) Project objectives

Analyzed genomic data will origin from 


## 2) Tools used in the project
* Python
* Pandas
* Seaborn
* Statistics (significance testing, pingouin and scikit_posthocs libraries)

## 3) Data colletion
