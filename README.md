# Program-CPP-Daniel-PAnggabean_Calypso_TLS25

#include <iostream>
#include <string>
using namespace std;

// Fungsi user-defined untuk membalik string
string myReverse(string text) {
    int n = text.length();
    string result = "";
    for (int i = n - 1; i >= 0; i--) {
        result += text[i];
    }
    return result;
}

// Mesin pembuat kata sandi
string encrypt(string plain) {
    // Simpan ASCII ke array integer
    int n = plain.length();
    int arr[100];
    for (int i = 0; i < n; i++) {
        arr[i] = (int)plain[i]; // simpan ASCII
    }

    // Ubah lagi ke char tapi dalam bentuk terbalik
    string encrypted = "";
    for (int i = n - 1; i >= 0; i--) {
        encrypted += (char)arr[i];
    }
    return encrypted;
}

// Mesin pembalik kata sandi → kata asli
string decrypt(string cipher) {
    // Proses sama, tinggal balik lagi
    return myReverse(cipher);
}

int main() {
    string kata;
    cout << "Masukkan kata asli: ";
    getline(cin, kata);

    string sandi = encrypt(kata);
    cout << "Hasil enkripsi (sandi): " << sandi << endl;

    string asli = decrypt(sandi);
    cout << "Hasil dekripsi (kata asli): " << asli << endl;

    return 0;
}


#include <iostream>
using namespace std;

int main() {
    int waktu;
    cout << "Masukkan detik ke: ";
    cin >> waktu;

    // Misal siklus total 3 detik (Hijau=0, Kuning=1, Merah=2)
    int fase = waktu % 3;

    string lampu[3] = {"Hijau", "Kuning", "Merah"};

    cout << "Lampu pada detik " << waktu << " adalah: " << lampu[fase] << endl;

    return 0;
}
