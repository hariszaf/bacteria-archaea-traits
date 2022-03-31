# GOLD notes

Data obtained from the JGI genome online database (GOLD). 

https://gold.jgi.doe.gov/

This data cannot be downloaded in its entirety from the website, and direct contact with JGI is therefore required.However, an older version is available here.

- The GOLD metadata export is very large and left as two zipped files:

(1) `Mark_Westoby_Organism_Metadata_Export_02152018.txt.zip`
This file contains the main trait data for each organism

(2) `Mark_Westoby_Genome_Size_Details_Export_02152018.txt.zip`
This file contains genome size estimates and are linked to the main data file using the gold organism id.

- To load the GOLD data, you need to unzip the two files. 

Since much of the GOLD data is input by individual users, there are a considerable number of inconsistencies, which is sorted out in the preparation process. 

This includes 

- conversion of different units to consistent terminology (i.e. "microns" -> "um") as well as same unit through calculation (i.e. "nm" -> "um")
- removal of units for temperature (i.e. "C", "degrees", "celsius"...)
- splitting different size range formats into separate columns and ensuring "length" is longer than "width".

# Update on 06/10/2020
New GOLD dataset included:

(3) GOLD_Organism_Metabolism_08252020.csv

This file contains metabolism (metabolic pathway) data from the GOLD database
This is merged into above main GOLD data during prep..


# Update on 2022, March

GOLD database now provides some important files like the ones used above (`Mark_Westoby*`).

You may find them at: https://gold.jgi.doe.gov/downloads .

The `Public Studies/Biosamples/SPs/APs/Organisms Excel` is a `.xlsx` file that includes 5 tabs. 
As mentioned in the `README` tab of the file: 

-----------
This file contains an export of the public data in Genomes Online Database (GOLD) along with some key metadata fields. 
Each tab in this Excel represents the four levels in which data is organized in GOLD namely Study, Biosample/Organism, Sequencing Project and Analysis Project.

Every Sequencing Project in this excel is connected to a Study. 
Additionally a Sequencing Project is connected to either a Biosample or an Organism based on the type of sample that is being sequenced. 
A metagenome Sequencing Project will be connected to a Biosample whereas a WGS Sequencing Project will be associated with an Organism.

Please note that this excel is not meant to replicate the exact user experience of the GOLD website but its purpose is to provide access to the bulk of normalized data to our users.  
A brief description of each of the five tabs in this excel and how these are interconnected is provided below along with examples:

Study (Gs): A GOLD Study broadly represents the overall goal of a research proposal that a researcher sets out to explore. E.g. Gs0114820

Biosample (Gb): A GOLD Biosample applies to Metagenome or Metatranscriptome projects only and describes the environment from where the sample for a sequencing project was collected. E.g. Gb0239762

Organism (Go): A GOLD Organism corresponds to any living biological material (bacteria, virus, fungi, plant, and animal) that is associated with a Sequencing Project. E.g. Go0459731

Sequencing Project (Gp): A GOLD Sequencing Project represents individual sequencing deliverables from an Organism or Biosample that is targeted for sequencing.
E.g. Gp0326772 is an isolate Whole Genome Sequencing project. Hence it is connected to GOLD organism Go0459731.
E.g. Gp0452338 is a metagenome sequencing project. Hence it is connected to GOLD Biosample Gb0239762.
These two sequencing projects are both part of GOLD Study Gs0114820.

Analysis Project (Ga): A GOLD Analysis Project is the informatics processing of a Sequencing Project.  It describes how the assembly and annotation of a Sequencing Project were performed. E.g. Ga0314271 is based on the isolate Whole Genome Sequencing project; hence it is connected to Gp0326772.


-------

Tab 5 (`Sequencing Project`) includes the `PROJECT STATUS` column that is used from the `Mark_Westoby_Genome_Size_Details_Export` file. 

Tab 4 (`Organism`) includes the matadata needed. 

By converting the `.xlsx` file to `.tsv` we can edit the `preparation` script to work with those files instead. 








