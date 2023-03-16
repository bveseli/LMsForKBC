This data set is made available under a Creative Commons License:
http://creativecommons.org/licenses/by-sa/3.0/

You are free:
 to Share — to copy, distribute and transmit the work
 to Remix — to adapt the work
 to make commercial use of the work

Under the following conditions:

 Citing: when using this data set, cite the related paper "Evaluating Language Models for Knowledge Base      
         Completion" by [will be included upon publication]
    
    
# WD_Known

This folder contains pickled files for 41 relations. Again, each file contains only the facts of one relation and which relation is specified by the filename. Each file contains only the triples from WD_KNOWN(without_labels) for whose subjects and objects a natural language label was also found.


Structure: 

    Each pickled file is a python list of 5-tuples:
    
        [(relation, relation_description, template, subject_wikidataID, subject_label, 
          object_wikidataID, object_label),......]

          
    If a subject has more than one valid object, it will appear more than one time in this list: one time for each valid object.
    
    
# WD_Known(lama_format)

This folder contains the same triples per relation as in folder WD_Known, but in LAMA-format, so that using the LAMA Framework by Petroni et al. on WD-Known is easily possible. Please note that the triples, where subject and/or object has no label, have to be filtered before using LAMA. 


# missing_facts

#### pickled-files

Each file in this folder contains 10,000 sampled subjects per relation with missing objects in Wikidata. The subjects of each relation are conditioned on having the 1 (up to 2) most frequent relation-compatible entity type:

    P27   --> subject entity types: human,fictional human
    P103  --> subject entity types: human, ethnic group
    P1412 --> subject entity types: human
    P159  --> subject entity types: business, enterprise
    P176  --> subject entity types: supercomputer, ship
    P178  --> subject entity types: video game, software
    P364  --> subject entity types: films, television series episode


Structure:

    Each pickled file is a python dictionary, where the subject Wikidata ID is the key and the subject label is the value
    
        {subject_wikidataID:subject_label, ....}
        
        
#### mturk_annotations.csv

This folder contains 50 high accuracy predictions (by BERT) for 50 missing facts per relation. File contains our annotations, as well as the mturk annotations (columns with prefix: mturk_)


