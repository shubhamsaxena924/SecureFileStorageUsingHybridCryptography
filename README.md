# Secure File Storage Using Hybrid Cryptography

## Objective: To achieve a highly secure platform for storing any type of file on Cloud using Hybrid Cryptography Technique.</br>

### Hybrid Cryptography: Combination of multiple cryptographic technique to get even more secure and strong cryptographic system.</br> </br>

# Methodology

To achieve the above goal, the following methodology happens on sender side:</br>

1. Load the file on the server. It can be any type of file.</br>
2. Dividing the uploaded file into N parts depending on the fixed block size.</br>
3. Encrypting all the sub-files using any one of the selected algorithms (Algorithm is changed with every part in round robin fashion).</br>
4. The keys for cryptography algorithms used are stored in a file and then the resulting file is secured using a different cryptographic algorithm and the key for this algorithm is provided to the user as public key, which needs to be transferred safely to the receiver. (Currently, we are using symmetric encryption, we may also shift to authentication and asymmetric encryption in future.)</br>

After the above steps on the sender side, you will have N files which are in encrypted form which are stored on the server and a key which is downloaded as public key for decrypting the file and downloading it.</br>

To restore the file:</br>

1. Load the key (.pem file) on the server. Ask it from your sender.</br>
2. Decrypt the keys of the algorithms.</br>
3. Decrypt all the N subfiles using the same algorithms which were used to encrypt them.</br>
4. Combine all the N subfiles to form the original file and provide it to the user for downloading.</br>

# How to Run

**NOTE:** The project is based on Python 3.8.10 platform.</br>

Libraries Used:

1. Flask 1.1.1
2. werkzeug
3. Cryptography 2.9.2

Step 1: Install Requirements</br>
`pip install -r requirements.txt`</br>

Step 2: Run the application</br>
`python3 app.py` or try `python app.py`</br>

Step 3: Visit the localhost on your browser</br>

Step 4: Enjoy :)
