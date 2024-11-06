# Latihan

![image](https://github.com/user-attachments/assets/5b136221-3417-41da-a2ab-1f77a653535d)

Dari modul praktikum 3, tambahkan constructor pada masing-masing class dan tambahkan overload dan override constructor tersebut.
Contoh: Programmer(”Andi Herlambang”), Programmer(”Riko”, 6000000), Programmer(”Dina”, 5000000, 3000000)

# Penjelasan program beserta hasil eksekusi program
# -  Class pegawai
  ```
public class Pegawai {
    private String nama;
    private double gajiPokok;

    // Default constructor
    public Pegawai() {
        this.nama = "Unknown";
        this.gajiPokok = 0.0;
    }

    // Overloaded constructor with one parameter
    public Pegawai(String nama) {
        this.nama = nama;
        this.gajiPokok = 0.0; // Default gajiPokok to 0
    }

    // Overloaded constructor with two parameters
    public Pegawai(String nama, double gajiPokok) {
        this.nama = nama;
        this.gajiPokok = gajiPokok;
    }

    // Setters and Getters
    public void setNama(String nama) {
        this.nama = nama;
    }

    public String getNama() {
        return nama;
    }

    public void setGajiPokok(double gajiPokok) {
        this.gajiPokok = gajiPokok;
    }

    public double getGajiPokok() {
        return gajiPokok;
    }

    // Method to print information
    public void cetakInfo() {
        System.out.println("Nama: " + nama);
        System.out.println("Gaji Pokok: " + gajiPokok);
    }
}
```
- Variabel nama dan gajiPokok: Properti untuk menyimpan nama dan gaji pokok pegawai.
- Constructor:
  - Default Constructor: Menginisialisasi nama dengan "Unknown" dan gajiPokok dengan 0.0.
  - Overloaded Constructor (1 parameter): Menginisialisasi nama sesuai dengan parameter, dan gajiPokok tetap 0.0.
  - Overloaded Constructor (2 parameter): Menginisialisasi nama dan gajiPokok sesuai dengan nilai parameter yang diberikan.
- Method setNama dan getNama: Digunakan untuk mengatur dan mengambil nilai nama.
- Method setGajiPokok dan getGajiPokok: Digunakan untuk mengatur dan mengambil nilai gajiPokok.
- Method cetakInfo: Mencetak informasi nama dan gajiPokok ke konsol.

# - Class Manager
```
public class Manager extends Pegawai {
    private double tunjangan;

    // Default constructor
    public Manager() {
        super();
        this.tunjangan = 0.0;
    }

    // Overloaded constructor with one parameter
    public Manager(String nama) {
        super(nama);
        this.tunjangan = 0.0;
    }

    // Overloaded constructor with two parameters
    public Manager(String nama, double gajiPokok) {
        super(nama, gajiPokok);
        this.tunjangan = 0.0;
    }

    // Overloaded constructor with all parameters
    public Manager(String nama, double gajiPokok, double tunjangan) {
        super(nama, gajiPokok);
        this.tunjangan = tunjangan;
    }

    // Setter and Getter for tunjangan
    public void setTunjangan(double tunjangan) {
        this.tunjangan = tunjangan;
    }

    public double getTunjangan() {
        return tunjangan;
    }

    // Override cetakInfo to include tunjangan
    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.println("Tunjangan: " + tunjangan);
    }
}
```
- Variabel tunjangan: Menyimpan tunjangan yang diterima oleh seorang manajer.
- Constructor:
  - Default Constructor: Memanggil constructor Pegawai dengan super() dan menginisialisasi tunjangan ke 0.0.
  - Overloaded Constructor (1 parameter): Memanggil constructor Pegawai dengan satu parameter nama dan mengatur tunjangan ke 0.0.
  - Overloaded Constructor (2 parameter): Memanggil constructor Pegawai dengan nama dan gajiPokok, lalu mengatur tunjangan ke 0.0.
  - Overloaded Constructor (3 parameter): Memanggil constructor Pegawai dengan nama dan gajiPokok, serta menginisialisasi tunjangan sesuai parameter.
- Method setTunjangan dan getTunjangan: Mengatur dan mengambil nilai tunjangan.
- Method cetakInfo (Override): Memanggil cetakInfo dari Pegawai dengan super.cetakInfo(), lalu menambahkan informasi tunjangan.

# - Class Programmer
```
public class Programmer extends Pegawai {
    private double bonus;

    // Default constructor
    public Programmer() {
        super();
        this.bonus = 0.0;
    }

    // Overloaded constructor with one parameter
    public Programmer(String nama) {
        super(nama);
        this.bonus = 0.0;
    }

    // Overloaded constructor with two parameters
    public Programmer(String nama, double gajiPokok) {
        super(nama, gajiPokok);
        this.bonus = 0.0;
    }

    // Overloaded constructor with all parameters
    public Programmer(String nama, double gajiPokok, double bonus) {
        super(nama, gajiPokok);
        this.bonus = bonus;
    }

    // Setter and Getter for bonus
    public void setBonus(double bonus) {
        this.bonus = bonus;
    }

    public double getBonus() {
        return bonus;
    }

    // Override cetakInfo to include bonus
    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.println("Bonus: " + bonus);
    }
}
```
- Variabel bonus: Menyimpan bonus yang diterima oleh seorang programmer.
- Constructor:
  - Default Constructor: Memanggil constructor Pegawai dengan super() dan menginisialisasi bonus ke 0.0.
  - Overloaded Constructor (1 parameter): Memanggil constructor Pegawai dengan nama dan mengatur bonus ke 0.0.
  - Overloaded Constructor (2 parameter): Memanggil constructor Pegawai dengan nama dan gajiPokok, lalu mengatur bonus ke 0.0.
  - Overloaded Constructor (3 parameter): Memanggil constructor Pegawai dengan nama dan gajiPokok, serta menginisialisasi bonus sesuai parameter.
- Method setBonus dan getBonus: Mengatur dan mengambil nilai bonus.
- pMethod cetakInfo (Override): Memanggil cetakInfo dari Pegawai dengan super.cetakInfo(), lalu menambahkan informasi bonus.

# - Class Main
```
public class Main {
    public static void main(String[] args) {
        // Using the default constructor for Manager
        Manager manajer = new Manager();
        manajer.setNama("Budi");
        manajer.setGajiPokok(5000000);
        manajer.setTunjangan(2000000);
        manajer.cetakInfo();

        System.out.println();

        // Using the overloaded constructors for Programmer
        Programmer programmer1 = new Programmer("Andi Herlambang");
        programmer1.cetakInfo();

        System.out.println();

        Programmer programmer2 = new Programmer("Riko", 6000000);
        programmer2.cetakInfo();

        System.out.println();

        Programmer programmer3 = new Programmer("Dina", 5000000, 3000000);
        programmer3.cetakInfo();
    }
}
```
- Objek Manager: Dibuat dengan constructor default, lalu menggunakan setNama, setGajiPokok, dan setTunjangan untuk mengatur nilainya.
- Objek Programmer:
  - programmer1: Dibuat menggunakan constructor dengan satu parameter (nama).
  - programmer2: Dibuat menggunakan constructor dengan dua parameter (nama, gajiPokok).
  - programmer3: Dibuat menggunakan constructor dengan tiga parameter (nama, gajiPokok, bonus).
- Method cetakInfo

# - Hasil Output
![Screenshot 2024-11-06 175929](https://github.com/user-attachments/assets/f3a66c63-bd49-4a79-9c1b-7e6483661f4d)
