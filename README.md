## Step 1
```
#req.txt can be found from the above repository link 
pip install -r req.txt
```
Install python module
```
openssl ecparam -name prime256v1 -genkey -noout -out vapid_private.pem
```
Create pem for generate private,public Key

```
openssl ec -in ./vapid_private.pem -outform DER|tail -c +8|head -c 32|base64|tr -d '=' |tr '/+' '_-' >> private_key.txt
openssl ec -in ./vapid_private.pem -pubout -outform DER|tail -c 65|base64|tr -d '=' |tr '/+' '_-' >> public_key.txt
```

Generate private, public key and store to txt file.

## Step 2 
```
python main.py
```
And Access to 127.0.0.1:8080

## Step 3
Test Web push