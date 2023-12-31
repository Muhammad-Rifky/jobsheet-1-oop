# **Laporan Praktikum**
# **Jobsheet 1 OOP**

## **Data Mahasiswa**
><p>Nama : Muhammad Rifky Harto Biantoro<p>
>Kelas : 2F<p>
>Prodi : D-IV Teknik Inormatika<p>
>Jurusan : Teknologi Inormasi<p>
>Politeknik Negeri Malang

<br>

## **16.1 Tujuan Praktikum**
Setelah melakukan praktikum ini, mahasiswa mampu:<p>
1. Perbedaan paradigma berorientasi objek dengan paradigma struktural
2. Konsep dasar PBO


<br>

## **3 Percobaan**
### **3.1 Langkah-langkah Percobaan 1**
Didalam percobaan ini, kita akan mendemonstrasikan bagaimana membuat class, membuat object,
kemudian mengakses method didalam class tersebut.<p>


1. Buka Netbeans, buat project SepedaDemo.
    <img src="SepedaDemo.png"><p>

2. Buat class Sepeda. Klik kanan pada package sepedademo – New – Java Class.
    <img src="Sepeda.png"><p>
    ```java
    
    ```
3. Ketikkan kode class Sepeda dibawah ini.
   <img src="contohsepeda.png"><p>
5. 
### **16.2.2 Verifikasi Hasil Percobaan**
Setelah saya melakukan RUN kode program diatas didapatkan hasil run sama seperti gambar dibawah ini<p>
<img src="Images/2.PNG"><p>


<br>

### **16.2.3 Pertanyaan Percobaan**
1. Perhatikan baris kode 25-36, mengapa semua jenis data bisa ditampung ke dalam sebuah Arraylist?<p>
    >**Jawab**<p>
    >Karena arrayList tersebut tidak terdapat kurung sudut yang menyimpan secara spesifik data yang akan disimpan didalamnya. sehingga arrayylist pada baris kode 25-36 diatas bersifat sintak umum yang dapat menyimpan data segala jenis tipe data<P>

2. Modifikasi baris kode 25-36 seingga data yang ditampung hanya satu jenis atau spesifik tipe tertentu!<p>
    >**Jawab**<p>
    ```java
     List <Integer> l = new ArrayList();
        
        l.add(1);
        l.add(2);
        l.add(3);
        //l.add("Cireng");
        System.out.printf("Elemen 0 : %d total elemen : %d elemen terakhir : %s\n", 
                l.get(0), l.size(), l.get(l.size() - 1));
        l.add(4);
        l.remove(0);
        System.out.printf("Elemen 0 : %d total elemen : %d elemen terakhir : %s\n", 
                l.get(0), l.size(), l.get(l.size() - 1));
    ```

3. Ubah kode pada baris kode 38 menjadi seperti ini<p>
    <img src="Images/3.PNG"><p>
    >**Jawab**<p>
    ```java
    LinkedList<String> names = new LinkedList<>();
        names.add("Noureen");
        names.add("Akhleema");
        names.add("Shannum");
        names.add("Uwais");
        names.add("Al-Qarni");
    ```

4. Tambahkan juga baris berikut ini, untuk memberikan perbedaan dari tampilan yang sebelumnya<p>
    <img src="Images/4.PNG"><p>
    >**Jawab**<p>
    ```java
    LinkedList<String> names = new LinkedList<>();
        names.add("Noureen");
        names.add("Akhleema");
        names.add("Shannum");
        names.add("Uwais");
        names.add("Al-Qarni");
        System.out.printf("Elemen 0 : %s total elemen : %s elemen terakhir : %s\n", 
                names.get(0), names.size(), names.get(names.size() - 1));
        names.set(0, "My Kid");
        System.out.printf("Elemen 0 : %s total elemen : %s elemen terakhir : %s\n", 
                names.get(0), names.size(), names.get(names.size() - 1));
        System.out.println("Names : "+ names.toString());
        
        names.push("Mei-mei");
        System.out.printf("Elemen 0: %s total elemen : %s elemen terakhir : %s\n",
                names.getFirst(), names.size(), names.getLast());
        System.out.println("Names : "+ names.toString());
    ```

5. Dari penambahan kode tersebut, silakan dijalankan dan apakah yang dapat Anda jelaskan!<p>
    >**Jawab**<p>
    <img src="Images/9.PNG"><p>
    yang dapat saya jelaskan adalah kita dapat membatasi tipe data yang akan dimasukkan dengan perintah <tipe data>, dengan menggunakan class LinkedList kita dapat menggunakan method linked list seperti push(), getFirst(), getLast(), akan tetapi ketika menggunakan class List tidak bisa<p>

<br>

## **16.3 Kegiatan Praktikum 2**

<br>

### **14.3.1 Langkah langkah percobaan**
Pada praktikum 2 ini akan dibuat beberapa method untuk menampilkan beberapa cara yang dapat dilakukan untuk mengambil/menampilkan elemen pada sebuah collection. Silakan ikutilah Langkah-langkah di bawah ini<p>

1. Buatlah class dengan nama LoopCollection serta tambahkan method main yang isinya adalah sebagai berikut.<p>

    <img src="Images/5.PNG"><p>
    ```java
    package Praktikum2;
    import java.util.Stack;
    import java.util.Iterator;
    /**
    *
    * @author Alvian
    */
    public class loopCollection {
        /**
        * @param args the command line arguments
        */
        public static void main(String[] args) {
            Stack<String> fruits = new Stack<>();
            fruits.push("Banana");
            fruits.add("Orange");
            fruits.add("Watermelon");
            fruits.add("Leci");
            fruits.push("Salak");
        
            for(String fruit : fruits){
                System.out.printf("%s ", fruit);
            }
            System.out.println("\n"+ fruits.toString());
        
            while(!fruits.empty()){
                System.out.printf("%s ", fruits.pop());
            }
    ```

2. Tambahkan potongan kode berikut ini dari yang sebelumnya agar proses menampilkan elemen pada sebuah stack bervariasi.

    ```java
        fruits.push("Melon");
            fruits.push("Durian");
            System.out.println("");
            for(Iterator<String> it = fruits.iterator(); it.hasNext();){
                String fruit = it.next();
                System.out.printf("%s ", fruit);
            }
            System.out.println("");
            fruits.stream().forEach(e -> {
                System.out.printf("%s ",e);
            });
            System.out.println("");
            for(int i=0; i<fruits.size(); i++){
                System.out.printf("%s ", fruits.get(i));
            }
        }
    }
    ```

<br>

### **16.3.2 Verifikasi Hasil Percobaan**
Setelah saya melakukan RUN kode program diatas didapatkan hasil run seperti berikut ini<p>
<img src="Images/6.PNG"><p>

<br>

### **16.3.3 Pertanyaan Percobaan**
1. Apakah perbedaan fungsi push() dan add() pada objek fruits?<p>
    > **Jawab**<p>
    >fungsi push() dan add() diatas sama sama menambahkan elemen, yang membedakan adalah<p>
    >- push() merupakan fungsi dari interface stack
    >- add() tidak atau bukan interface dari stack

2. Silakan hilangkan baris 43 dan 44, apakah yang akan terjadi? Mengapa bisa demikian?<p>
    > **Jawab**<p>
    ```java
    //fruits.push("Melon");
    //fruits.push("Durian");
    ```
    hasil output<p>
    <img src="Images/10.PNG"><p>
    yang terjadi adalah data "melon" dan "durian" tidak muncul, karena saat kita mengakses fungsi push() artinyya kita akan menambahkan data "melon" dan "durian"<p>

3. Jelaskan fungsi dari baris 46-49?<p>
    >**Jawab**<p>
    >- pada baris 46 berfungsi untuk proses inisialisasi dan mengatur aturan perulangan sesuai perintah yang di instruksikan
    >- pada baris 47 adalah untuk pembuatan variabel fruit menjadi it.next()
    >- pada baris 48 berfungsi untuk mencetak variabel fruit<p>

4. Silakan ganti baris kode 25, Stack<String> menjadi List<String> dan apakah yang terjadi? Mengapa bisa demikian?<p>
    > **Jawab**<p>
    ><img src="Images/11.PNG"><p>
    >yang terjadi adalah eror pada bagian push, empty, pop karena tidak dapat dijalankan pada interface list, yang mana perintah yang diatas adalah fungsi dari interface stack<p>

5. Ganti elemen terakhir dari dari objek fruits menjadi “Strawberry”!
    > **Jawab**<p>
    ><img src="Images/12.PNG"><p>

6. Tambahkan 3 buah seperti “Mango”,”guava”, dan “avocado” kemudian dilakukan sorting!
    > **Jawab**<p>
    ```java
    package Praktikum2;
    import java.util.Stack;
    import java.util.Iterator;
    import java.util.Collections;
    /**
    *
    * @author Alvian
    */
    public class loopCollection {
        /**
        * @param args the command line arguments
        */
        public static void main(String[] args) {
            Stack<String> fruits = new Stack<>();
            fruits.push("Banana");
            fruits.add("Orange");
            fruits.add("Watermelon");
            fruits.add("Leci");
            fruits.push("Salak");
        
        
            for(String fruit : fruits){
                System.out.printf("%s ", fruit);
            }
            System.out.println("\n"+ fruits.toString());
        
            while(!fruits.empty()){
                System.out.printf("%s ", fruits.pop());
            }
            fruits.push("Melon");
            fruits.push("Strawberry");
            System.out.println("");
            for(Iterator<String> it = fruits.iterator(); it.hasNext();){
                String fruit = it.next();
                System.out.printf("%s ", fruit);
            }
            System.out.println("");
            fruits.stream().forEach(e -> {
                System.out.printf("%s ",e);
                });
            System.out.println("");
            for(int i=0; i<fruits.size(); i++){
                System.out.printf("%s ", fruits.get(i));
            }
            //Tambahkan 3 buah seperti “Mango”,”guava”, dan “avocado” kemudian dilakukan sorting!
            fruits.push("Manggo");
            fruits.push("Guava");
            fruits.push("Avocado");
        
            System.out.println("");
            System.out.println("\nData sesudah disorting ");
            Collections.sort(fruits);
            Iterator i= fruits.iterator();
        
            while(i.hasNext()){
                System.out.print(i.next() + "  ");
                System.out.println("");
            } 
        } 
    }
    ```
    dengan output sebagai berikut
    <img src="Images/13.PNG"><p>

<br>

## **16.4 Kegiatan Praktikum 3**

<br>

### **16.4.1 Langkah langkah percobaan**
Pada praktikum 3 ini dilakukan uji coba untuk mengimplementasikan sebuah collection untuk menampung objek yang dibuat sesuai kebutuhan. Objek tersebut adalah sebuah objek mahasiswa dengan fungsi-fungsi umum seperti menambahkan, menghapus, mengubah, dan mencari.<p>

1. Buatlah sebuah class Mahasiswa dengan attribute, kontruktor, dan fungsi sebagai berikut.<p>

    <img src="Images/7.PNG"><p>
    ```java
    package Praktikum3;
    /**
    *
    * @author Alvian
    */
    public class mahasiswa {
        String nim;
        String nama;
        String notelp;
    
        public mahasiswa(){
        
        }
        public mahasiswa(String nim, String nama, String notelp){
            this.nim = nim;
            this.nama = nama;
            this.notelp = notelp;
        }
        @Override
        public String toString(){
            return "mahasiswa{" +"nim= "+nim +", nama= "+nama+", notelp= "+notelp+ '}';
        }
    }
    ```

2. Selanjutnya, buatlah sebuah class ListMahasiswa yang memiliki attribute seperti di bawah ini<p>

    <img src="Images/7.PNG"><p>
    ```java
    package Praktikum3;
    import java.util.ArrayList;
    import java.util.Arrays;
    import java.util.List;
    /**
    *
    * @author Alvian
    */
    public class listMahasiswa {
    
        List<mahasiswa> mahasiswas = new ArrayList<>();
    ```

3. Method tambah(), hapus(), update(), dan tampil() secara berurut dibuat agar bisa melakukan operasi-operasi seperti yang telah disebutkan.<p>

    ```java
    public void tambah(mahasiswa... Mahasiswa){
            mahasiswas.addAll(Arrays.asList(Mahasiswa));
    }
    public void hapus(int index){
        mahasiswas.remove(index);
    }
    public void update(int index, mahasiswa mhs){
        mahasiswas.set(index, mhs);
    }
    public void tampil(){
        mahasiswas.stream().forEach(mhs -> {
            System.out.println(""+ mhs.toString());
        });
    }
    ```

4. Untuk proses hapus, update membutuhkan fungsi pencarian terlebih dahulu yang potongan kode programnya adalah sebagai berikut

    ```java
    int linearSearch(String nim){
        for(int i=0; i<mahasiswas.size(); i++){
            if(nim.equals(mahasiswas.get(i).nim)){
                return i;
            }
        }
        return -1;
    }
    ```

5. Pada class yang sama, tambahkan main method seperti potongan program berikut dan amati hasilnya!<p>

    ```java
    public static void main(String[] args) {
        listMahasiswa lm = new listMahasiswa();
        mahasiswa m = new mahasiswa("201234", "Noureen", "021xx1");
        mahasiswa m1 = new mahasiswa("201235", "Akhleema", "021xx2");
        mahasiswa m2 = new mahasiswa("201236", "Shannum", "021xx3");
        //menambahkan objek mahasiswa
        lm.tambah(m, m1, m2);
        //menampilkan list mahasiswa
        lm.tampil();
        //update mahasiswa
        lm.update(lm.linearSearch("201235"), new mahasiswa("201235", "Akhleema Lela", "021xx2"));
        System.out.println("");
        lm.tampil();
    } 
    ```
<br>

### **16.4.2 Verifikasi Hasil Percobaan**
Setelah saya melakukan RUN kode program diatas didapatkan hasil run seperti berikut ini<p>
<img src="Images/8.PNG"><p>

<br>

### **16.4.3 Pertanyaan Percobaan**
1. Pada fungsi tambah() yang menggunakan unlimited argument itu menggunakan konsep apa? Dan kelebihannya apa?<p>
    > **Jawab**<p>
    >Pada fungsi tambah() menggunakan konsep atau method addAll() dari collections dimana konsep ini memiliki kelebihan dapat menambahkan element tanpa ada batas jumlah elemen yang ditambahkan<p>

2. Pada fungsi linearSearch() di atas, silakan diganti dengan fungsi binarySearch() dari collection!
    > **Jawab**<p>
    ```java
    int binarySearch(String nim){
        return Collections.binarySearch(mahasiswas, new mahasiswa(nim, null, null), new Comparator<mahasiswa>(){
            @Override
            public int compare(mahasiswa o1, mahasiswa o2){
                return o1.nim.compareTo(o2.nim);
            }
        });
    }
    ```
    dengan hasil output seperti dibawah ini<p>
    <img src="Images/15.PNG">


3. Tambahkan fungsi sorting baik secara ascending ataupun descending pada class tersebut!
    > **Jawab**<p>
    ascending
    ```java
    void ascSort(){
        Collections.sort(mahasiswas, new Comparator<mahasiswa>(){
            @Override
            public int compare(mahasiswa o1, mahasiswa o2){
                return o1.nim.compareTo(o2.nim);
            }
        });
    }
    ```
    descending
    ```java
    void dscSort(){
        Collections.reverse(mahasiswas);
    }
    ```
    berikut hasil outputnya<p>
    <img src="Images/14.PNG">

<br>

## **16.5 Tugas Praktikum**

1. Implementasikan stack menggunakan collection dengan contoh kasus tumpukan daftar film sesuai dengan fitur-fitur yang ditunjukkan pada gambar di bawah ini!<p>
    
    **JAWAB**<p>
    class "film<p>
    ```java
    package Tuggas1;
    /**
    *
    * @author Alvian
    */
    public class film {
        String id, judul, tahun, director;
    
        public film(String id, String judul, String tahun, String director){
            this.id = id;
            this.judul = judul;
            this.tahun = tahun;
            this.director = director;
        }
        @Override
        public String toString(){
            return "FILM {Id Film= "+id +", Judul FIlm= "+judul+", Tahun Tayang= "+tahun+", Director= "+director+"}";
        }
    }
    ```
    Berikut adalah Main class nya "filmMain"
    ```java
    package Tuggas1;
    import java.util.Scanner;
    import java.util.Stack;
    import java.util.Comparator;
    /**
    *
    * @author Alvian
    */
    public class filmMain {

        /**
        * @param args the command line arguments
        */
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            Scanner sd = new Scanner(System.in);
            Scanner sa = new Scanner(System.in);
            
            Stack <film> films = new Stack();
            
            char pilih;
            int menu = 0;
            do{
                System.out.println("+======================================+");
                System.out.println("+ Data Film Layar Lebar Sepanjang Masa +");
                System.out.println("+======================================+");
                System.out.println("+1. Input Judul FIlm                   +");
                System.out.println("+2. Hapus Data Film Teratas            +");
                System.out.println("+3. Cek Judul Film Teratas             +");
                System.out.println("+4. Info semua judul Film              +");
                System.out.println("+5. Keluar                             +");
                System.out.println("+======================================+");
                System.out.print("+Pilih menu\t: ");
                menu = sd.nextInt();
                switch(menu){
                    case 1:{
                        do{ 
                        System.out.println("+=====================================+");
                        System.out.print(" Id Film\t: ");
                        String id = sc.nextLine();
                        System.out.print(" Judul Film\t: ");
                        String judul = sc.nextLine();
                        System.out.print(" Tahun Tayang\t: ");
                        String tahun = sc.nextLine();
                        System.out.print(" Director\t: ");
                        String director = sc.nextLine();
                        film data = new film(id, judul, tahun, director);
                        films.push(data);
                        System.out.println("Mau tambah data atau tidak Y/n");
                        pilih = sa.next().charAt(0);
                        System.out.println("");
                        
                        }while (pilih == 'y' || pilih == 'Y');
                        
                    }
                    break;
                    case 2 :{
                        System.out.println("+=====================================+");
                        System.out.println("+       Hapus Data Film Teratas       +");
                        System.out.println("+=====================================+");
                        System.out.println(films.pop());
                        System.out.println("");
                    }
                    break;
                    case 3:{
                        System.out.println("+=====================================+");
                        System.out.println("+           Judul Film Teratas        +");
                        System.out.println("+=====================================+");
                        System.out.println(films.peek());
                        System.out.println("");
                    }
                    break;
                    case 4:{
                        System.out.println("+=====================================+");
                        System.out.println("+        Info Semua Judul FIlm        +");
                        System.out.println("+=====================================+");
                        for(int i=0; i<films.size(); i++){
                            System.out.println(films.get(i));
                        }
                        System.out.println("");
                    }
                    break;
                    case 5: {
                        System.out.println("");
                        System.out.println("+            Terima Kasih             +");
                    }
                    break;
                }
            }while (menu < 5 && menu > 0);
        }
    }
    ```
    ### Output<p>
    ### Berikut adalah Hasil output menu 1<p>
    <img src="Images/16.PNG"><p>
    <img src="Images/17.PNG"><p>

    ### Berikut adalah Hasil output menu 2<p>
    <img src="Images/18.PNG"><p>

    ### Berikut adalah Hasil output menu 3<p>
    <img src="Images/19.PNG"><p>

    ### Berikut adalah Hasil output menu 4<p>
    <img src="Images/20.PNG"><p>

    ### Berikut adalah Hasil output menu 4<p>
    <img src="Images/21.PNG"><p>

    <br>

2. Buatlah implementasi program daftar nilai mahasiswa semester, minimal memiliki 3 class yaitu Mahasiswa, Nilai, dan Mata Kuliah. Khusus untuk data Mahasiswa dan Mata Kuliah harus sudah diinisialisasi, sehingga ketika memasukkan data nilai data mahasiswa dan mata kuliah cukup menginputkan nim ataupun kode mata kuliah. Yang paling penting adalah antara objek mahasiswa, matakuliah, dan nilai harus saling terhubung.<p>

     **JAWAB**<p>
    ### KODE PROGRAM<p>
    ### class "mahasiswa"
    ```java
    package Tuggas2;
    /**
    *
    * @author Alvian
    */
    public class mahasiswa {
        String nim, nama, noTelp;
        
        public mahasiswa(){
            
        }
        public mahasiswa(String nim, String nama, String noTelp){
            this.nim = nim;
            this.nama = nama;
            this.noTelp = noTelp;
        }
        @Override
        public String toString(){
            return String.format("%s\t%-15s\t%s", nim, nama, noTelp);
        }
    }
    ```
    ### class "mataKuliah"
    ```java
    package Tuggas2;
    /**
    *
    * @author Alvian
    */
    public class mataKuliah {
        String kodeMk, namaMk;
        int sks;
        
        public mataKuliah(String kodeMk, String namaMk, int sks){
            this.kodeMk = kodeMk;
            this.namaMk = namaMk;
            this.sks = sks;
        }
        public String toString(){
            return String.format("%s\t%-40s%s", kodeMk, namaMk, sks);
        }
    }
    ```
    ### class "nilaiMain"
    ```java
    package Tuggas2;
    import java.util.Scanner;
    import java.util.List;
    import java.util.ArrayList;
    import java.util.Arrays;
    import java.util.Comparator;
    /**
    *
    * @author Alvian
    */
    public class nilaiMain {
        String kodeNil;
        double nilai;
        mahasiswa mhs;
        mataKuliah mk;
        
        public nilaiMain(String kodeNil, double nilai, mahasiswa mhs, mataKuliah mk){
            this.kodeNil = kodeNil;
            this.nilai = nilai;
            this.mhs = mhs;
            this.mk = mk;
        }
        List<mahasiswa> mhsA = new ArrayList<>();
        List<mataKuliah> matkulA = new ArrayList<>();
        
        public void tambahMhs(mahasiswa... mahasiswa){
            mhsA.addAll(Arrays.asList(mahasiswa));
        }
        public void tambahMatkul(mataKuliah... matkul){
            matkulA.addAll(Arrays.asList(matkul));
        }
        public void tampilMhs(){
            mhsA.stream().forEach(mhs -> {
                    System.out.println("" + mhs.toString());
            });
        }
        public void tampilMatkul(){
            matkulA.stream().forEach(mk -> {
                    System.out.println("" + mk.toString());
            });
        }
        int linearSearchMhs(String nim){
                for(int i = 0; i < mhsA.size(); i++){ 
                    if(nim.equals(mhsA.get(i).nim)){
                        return i;
                    }
                }
                return -1;
        }
        int linearSearchMatkul(String matkul){
                for(int i = 0; i < matkulA.size(); i++){ 
                    if(matkul.equals(matkulA.get(i).kodeMk)){
                        return i;
                    }
                }
                return -1;
        }
        mahasiswa cariMhs(String nim){
            for(int i = 0; i < mhsA.size(); i++){
                if(nim.equals(mhsA.get(i).nim)){
                    return mhsA.get(i);
                }
            }
            return null;
        }
        mataKuliah cariMatkul(String matkul){
            for(int i = 0; i < matkulA.size(); i++){
                if(matkul.equals(matkulA.get(i).kodeMk)){
                    return matkulA.get(i);
                }
            }
            return null;
        }
        public String toString(int idx1, int idx2){
            return mhsA.get(idx1).nim + "\t" + mhsA.get(idx1).nama + "\t" + matkulA.get(idx2).namaMk + "\t" + matkulA.get(idx2).sks + "\t";
        }
        
        static Comparator<nilaiMain> CompNilai = (n1, n2) ->{
            if(n1.nilai < n2.nilai){
                return -1;
            } else if (n1.nilai > (n2).nilai){
                return 1;
            } else {
                return 0;
            }
        };
        //main 
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            Scanner sd = new Scanner(System.in);
            Scanner sb = new Scanner(System.in);
            
            List<nilaiMain> nill = new ArrayList<>();
            nilaiMain n = new nilaiMain("", 0, null, null);
            
            mahasiswa m1 = new mahasiswa("20001", "Natasha", "021xxx");
            mahasiswa m2 = new mahasiswa("20002", "Amanda", "021xxx");
            mahasiswa m3 = new mahasiswa("20003", "Iqball", "021xxx");
            mahasiswa m4 = new mahasiswa("20004", "Anggara", "021xxx");
            mahasiswa m5 = new mahasiswa("20005", "Guanna", "021xxx");
            mahasiswa m6 = new mahasiswa("20006", "Natasha", "021xxx");
            
            n.tambahMhs(m1, m2, m3, m4, m5, m6);
            
            mataKuliah mk1 = new mataKuliah("0001", "Internet of Things", 3);
            mataKuliah mk2 = new mataKuliah("0002", "Algoritma dan Struktur Data", 2);
            mataKuliah mk3 = new mataKuliah("0003", "Algoritma dan Pemrograman", 2);
            mataKuliah mk4 = new mataKuliah("0004", "Praktikum Algoritma dan Struktur Data", 3);
            mataKuliah mk5 = new mataKuliah("0005", "Algoritma dan Struktur Data", 3);
            
            n.tambahMatkul(mk1, mk2, mk3, mk4, mk5);
            
            nilaiMain n1 = null;
            String nimMhs, mkMhs;
            
            int menu = 0;
            do{
                System.out.println("+===================================================+");
                System.out.println("+ Sistem Pengelolahan Data Nilai Mahasiswa Semester +");
                System.out.println("+===================================================+");
                System.out.println(" 1. Input Nilai");
                System.out.println(" 2. Tampil Nilai");
                System.out.println(" 3. Mencari Nilai Mahasiswa");
                System.out.println(" 4. Urut Data Nilai");
                System.out.println(" 5. Keluar");
                System.out.println("+==================================================+");
                System.out.print("Pilih\t\t\t\t: ");
                menu = sd.nextInt();
                System.out.println("");
                
                switch(menu){
                    case 1 :
                        System.out.print("Kode\t\t\t\t: ");
                        String kd = sc.nextLine();
                        System.out.print("Nilai\t\t\t\t: ");
                        double nilMhs = sb.nextDouble();
                        System.out.println("");
                        
                        System.out.println("                    Daftar Mahasiswa               ");
                        System.out.println("====================================================");
                        System.out.println("NIM\tNama\t\tNo Telp");
                        n.tampilMhs();
                        System.out.println("---------------------------------------------------");
                        System.out.print("Pilih Mahasiswa by nim\t\t: ");
                        nimMhs = sc.nextLine();
                        mahasiswa mahaSiswas;
                        mahaSiswas = n.cariMhs(nimMhs);
                        
                        System.out.println("");
                        System.out.println("                    Daftar Mata Kuliah              ");
                        System.out.println("====================================================");
                        System.out.println("Kode\tMata Kuliah\t\t\t\tSKS");
                        n.tampilMatkul();
                        System.out.println("---------------------------------------------------");
                        System.out.print("Pilih Mata Kuliah by Kode\t:");
                        mkMhs = sc.nextLine();
                        mataKuliah mataKuliahs;
                        mataKuliahs = n.cariMatkul(mkMhs);
                        
                        n1 = new nilaiMain(kd, nilMhs, mahaSiswas, mataKuliahs);
                        
                        nill.add(n1);
                        System.out.println("");
                        break;
                        
                    case 2:
                        System.out.println("                  Daftar Nilai Mahasiswa           ");
                        System.out.println("====================================================");
                        System.out.println("NIM\tNama\tMata Kuliah\t\tSKS\tNilai");
                        for(int i=0; i<nill.size(); i++){
                            n.linearSearchMhs(nill.get(i).mhs.nim);
                            n.linearSearchMatkul(nill.get(i).mk.kodeMk);
                            System.out.println(n.toString(n.linearSearchMhs(nill.get(i).mhs.nim), n.linearSearchMatkul(nill.get(i).mk.kodeMk))+ nill.get(i).nilai);
                        }
                        System.out.println("");
                        break;
                        
                    case 3:
                        System.out.println("                  Daftar Nilai Mahasiswa           ");
                        System.out.println("====================================================");
                        System.out.println("NIM\tNama\tMata Kuliah\t\tSKS\tNilai");
                        int sks = 0;
                        for(int i=0; i<nill.size(); i++){
                            n.linearSearchMhs(nill.get(i).mhs.nim);
                            n.linearSearchMatkul(nill.get(i).mk.kodeMk);
                            System.out.println(n.toString(n.linearSearchMhs(nill.get(i).mhs.nim), n.linearSearchMatkul(nill.get(i).mk.kodeMk))+ nill.get(i).nilai);
                        }
                        System.out.println("---------------------------------------------------");
                        System.out.print("Masukkan Data Mahasiswa NIM\t\t: ");
                        String input = sc.nextLine();
                        System.out.println("");
                        for (int i = 0; i < nill.size(); i++){
                            if(input.equalsIgnoreCase(nill.get(i).mhs.nim)){
                                sks += n.matkulA.get(i).sks;
                                n.linearSearchMhs(nill.get(i).mhs.nim);
                                n.linearSearchMatkul(nill.get(i).mk.kodeMk);
                                System.out.println(n.toString(n.linearSearchMhs(nill.get(i).mhs.nim), n.linearSearchMatkul(nill.get(i).mk.kodeMk)) + nill.get(i).nilai);    
                            }
                        }
                        System.out.println("---------------------------------------------------");
                        System.out.println("Total SKS " + sks + " Telah Diambil");
                        System.out.println("");
                        break;
                        
                    case 4:
                        System.out.println("                  Daftar Mahasiswa                 ");
                        System.out.println("====================================================");
                        System.out.println("NIM\tNama\tMata Kuliah\t\tSKS\tNilai");
                        nill.sort(CompNilai);
                        for (int i = 0; i < nill.size(); i++){
                            n.linearSearchMhs(nill.get(i).mhs.nim);
                            n.linearSearchMatkul(nill.get(i).mk.kodeMk);
                            System.out.println(n.toString(n.linearSearchMhs(nill.get(i).mhs.nim), n.linearSearchMatkul(nill.get(i).mk.kodeMk)) + nill.get(i).nilai);
                        }
                        System.out.println("");
                        break;
                        
                    case 5:
                        System.out.println("+==================================================+");
                        System.out.println("+                    Terima Kasih                  +");
                        System.out.println("+==================================================+");
                        break;
                }
            } while (menu < 5 && menu > 0);
        }
    }
    ```


    ### Output<p>
    ### Hasil Output menu 1
    <img src="Images/22.PNG"><p>
    <img src="Images/23.PNG"><p>
    <img src="Images/24.PNG"><p>
    <img src="Images/25.PNG"><p> 

    ### Hasil Output menu 2
    <img src="Images/26.PNG"><p>

    ### Hasil Output menu 3
    <img src="Images/27.PNG"><p>

    ### Hasil Output menu 4
    <img src="Images/28.PNG"><p>

    ### Hasil Output menu 5
    <img src="Images/29.PNG"><p>

    <br>

----------------------------
Terima Kasih<p>
Alvian Nur Firdaus | TI-1F | 2141720022 | Politeknik Negeri Malang<p>
copyright @2022 
_______________
