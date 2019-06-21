# Quillpad Transliteration Server

   Quillpad is an indic language input technology that revolutionized the Indian language typing scene. It is one of the most popular Indic input technologies with more than a billion words typed on the website alone.

   > Quillpad pioneered the successful use of machine learning for 
   > building a predictive language input technology. 
   > Quillpad has been rated as the best by many organisations that have embraced Quillpad.

   ### Version
   1.0.1

   ### Preparation

   There are several archive files in the repository which have to be extracted, these include trained transliteration models and additional text files necessary for the Quillpad Server

   *  CherryPy-3.2.2.tar.gz
   *  EnglishPronouncingTrees.tar.bz2
   *  IndianPronouncingTrees.tar.bz2
   *  additional_text_files.zip
   *  bengali.tar.bz2
   *  gujarati.tar.bz2
   *  hindi.tar.bz2
   *  kannada.tar.bz2
   *  malayalam.tar.bz2
   *  marathi.tar.bz2
   *  nepali.tar.bz2
   *  punjabi.tar.bz2
   *  tamil.tar.bz2
   *  telugu.tar.bz2
   *  unique_word_files.zip

   Kindly extract all of these archives into the repository folder itself.

   ### Installation

   Quillpad Server requires [Python 2.7](https://www.python.org/downloads/) to run.

   First, we need to compile the Quillpad Model loader that will be used to load the trained transliteration models

   ```sh
   $ cd Python\ Cart/python
   $ python setup.py build_ext --inplace
   $ cp QuillCCart.so ../../
   $ cd ../../
   ```

   Now, the Quillpad Server is ready to run

   ```sh
   $ python startquill_cherry.py
   ```

   ### Additional Information

   * Quillpad runs on port number 8090 (Additional configuration parameters are in *quill_cherry8088.conf*)

   * *processWordJSON* and *processWord* are the API endpoints over which the transliteration server can be accessed.
   > Example:

      * localhost:8090/processWordJSON?inString=hello&lang=hindi
      * localhost:8090/processWordJSON?inString=hello&lang=kannada

   ### Development

   Additional Quillpad Documentation coming soon. Thanks for your patience.

   ### Python Package Requirements
   CherryPy-3.2.2 -> included within the repo
   Pyrex -> http://www.cosc.canterbury.ac.nz/greg.ewing/python/Pyrex/
   		Need to download the source code from above link and use command `python setup.py install`
   MySQL and MySQL-python -> If error during Quillpad server startup, then check the page:
   		https://stackoverflow.com/questions/43634584/cant-install-mysql-python-with-pip-on-macos-10-12-4/54429707#54429707
   		If above link also does not work then you may have to download/ install via zip files
   		`pip install MySQL-python-1.2.5.zip` --> https://pypi.org/project/MySQL-python/#files
   		`pip install http://cdn.mysql.com/Downloads/Connector-Python/mysql-connector-python-2.0.4.zip`  
   		
   Need to make logs directory in Quillpad-Server:
   `mkdir logs`

   ### Reference
   An invited talk paper for the Quillpad project:
   https://www.aclweb.org/anthology/W12-4810
   
   Similar Google service integration:
   https://stackoverflow.com/questions/28707899/how-to-use-google-input-tools-in-website
