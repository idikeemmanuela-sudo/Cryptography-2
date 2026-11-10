# Cryptography-2
Hashing and encryption
openssl rand -base64 32 >key.bin
openssl rand -base64 16 >charlie.bin
openssl enc -aes-256-cbc -pbkdf2 -salt -in secretfile.txt -out secretfile.enc -pass file:./key.bin --iv $(cat charlie.bin | base64 --decode | xxd -p -c 32)       To encrypt information
ls (to confirm0
cat secretfile.enc            To view the encrypted file
openssl enc -d -aes-256-cbc -pbkdf2 -salt -in secretfile.enc -out secretfile_decrypted.txt -pass file:./key.bin --iv $(cat charlie.bin | base64 --decode | xxd -p -c 32)                    To decrypt information
ls
cat secretfile_decrypted.txt     To view the decrypted file.
