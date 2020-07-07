# GemDb37
MongoDb Variant database for human genome build 37, includes public annotations and various TGen projects.

Access -
Download Robo 3T (open source) or your favorite MongoDb GUI
	port: 25755
	server: labdb01.tgen.org
	
db: markers
collection: germline or tumor

--------------------------------------------------------------
Indexes -
    In Mongo since it is no-sql, it instead uses "indexes" on fields. When you look 
    under the 'tumor' collection there is a folder called 'Indexes'.  If you query using
    the fields that are listed there then your queries will be fast, otherwise they
    will be slow.

Queries (Quick Reference) - 
    Look up mongodb queries - they are "json" based so they are fairly straightforward, 
    although they can get more complex.
  
Examples -
 
    For searching on a patient:
    {'variants.studyPatient':'mystudy.mypatient'}

    For searching on a study:
    {'study':'myStudy'}

    If a patient has multiple samples:
    {'variants.projectRun':'myprojectrun'} 

-----------------------------------------------------------------------
VCF/Annotations -

    The VCF file is contained within the "variants" subdocument

    For searching a 'biomarker' event or 'variant':
        {'coord':'chr1:1038971:A:C'}

    As far as where the annotations/snpeff are (they are in subdocument structure):
        "annotate"    
        "snpeff"

-----------------------------------------------------------------------

Other important fields : 
        "effect" (contains gene and the mutation/event)
        "gene"
        "aberration" subdocument - contains mutation/event info
	"variants.filter" - PASS, LOWQC determined by GemDb.
