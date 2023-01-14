# UAS-KRIPTOGRAFI-ANGGUN
enkripsiXOR 
#include <iostream>
#include <string.h>
#include <fstream>
#include <stdlib.h>
using namespace std;

main(int argc, char *argv[])
{
	FILE *Fin, *Fout;
	char p, c;
	string K;
	int i;
	
	Fin = fopen(argv[1], "rb");
	if (Fin == NULL) {
		cout << "Berkas" << argv[1] <<" Tidak Ada " << endl;
		exit(0);
	}
	
	Fout = fopen(argv[2], "wb");
	
	cout << "Kata Kunci : ", cin >> K;
	cout << "Enkripsi" << argv[1] << "Menjadi" << argv[2] << "....";
	i = 0;
	while (!feof(Fin)) {
		p = getc(Fin);
		c = p ^ K[i];
		putc(c, Fout);
		i = (i + 1) % K.length();
	}
	fclose (Fin);
	fclose (Fout);
}
  
eksekusi cmd 
  ![image](https://user-images.githubusercontent.com/122099995/212473479-32e6f70e-e774-4073-bbca-d407380bd3d6.png)
  
enkripsi
  ![image](https://user-images.githubusercontent.com/122099995/212473553-978db1d3-870a-402b-866b-f383fc82071e.png)

  ![image](https://user-images.githubusercontent.com/122099995/212473563-55f82a7d-44f4-49a8-8110-5f434dd5437b.png)

DeskripsiXOR
  #include <iostream>
using namespace std;

string xorEncryptDecrypt(string toEncrypt, char key) {
    for (int i = 0; i < toEncrypt.size(); i++) {
        toEncrypt[i] = toEncrypt[i] ^ key;
    }
    return toEncrypt;
}

int main() {
    string plaintext = "Selamat dan Sukses Ujian Akhir Semester Gasal 2022-2023";
    char key = 'anggunsss';
    cout << "Plaintext : " << plaintext << endl;
    string ciphertext = xorEncryptDecrypt(plaintext, key);
    cout << "Ciphertext : " << ciphertext << endl;
    string decryptedtext = xorEncryptDecrypt(ciphertext, key);
    cout << "Decryptedtext : " << decryptedtext << endl;
    return 0;
}
 deskripsi
 ![image](https://user-images.githubusercontent.com/122099995/212473826-1de6c8b2-c4cc-416b-b4c9-b89d7cece97c.png)

  
