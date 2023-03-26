import java.util.ArrayList;
public class Main {
    private ArrayList <Mahasiswa> dataMasiswa;
    public static void main(String[] args) throws Exception {
        Main Screen = new Main();
        Screen.inputData();
        Screen.cetakData();
    }
    public void inputData() {
        dataMasiswa = new ArrayList<Mahasiswa>();
        String jawaban;
        int number = 1;
        do {
            System.out.println("________________________________");
            System.out.println("Data Mahasiswa ke "+number);
            System.out.print("NIM : ");
            String nim = System.console().readLine();
            System.out.print("Nama : ");
            String name = System.console().readLine();
            System.out.print("Jurusan : ");
            String jurusan = System.console().readLine();
            System.out.print("Tahun lahir : ");
            int tahun_lahir = Integer.parseInt(System.console().readLine());
            System.out.print("Jenis Kelamin: ");
            String Jenis_Kelamin = System.console().readLine();
            Mahasiswa mahasiswa = new Mahasiswa(name, nim, jurusan,tahun_lahir,Jenis_Kelamin);
            dataMasiswa.add(mahasiswa);
            System.out.print("Apakah Anda Ingin Menambahkan Nama Lagi? (Y/N)");
            jawaban = System.console().readLine();
            number++;
        } while (jawaban.equals("Y") || jawaban.equals("y"));
    }
    public void cetakData() {
        System.out.println("\n\n================================================================================================================");
        System.out.println("DAFTAR KELULUSAN MAHASISWA");
        System.out.println("==================================================================================================================");
        System.out.println("No\tNIM\t\tNama\t\tJurusan\t\t\tUmur\t\tJenis Kelamin");
        System.out.println("=================================================================================================================");


        int mahasiswa_laki = 0;
        int mahasiswa_perempuan = 0;
        int mahasiswa_ti = 0;
        int mahasiswa_si = 0;
        int mahasiswa_dkv = 0;
        

        // fungsi untuk menghitung jumlah jenis kelamin laki-laki atau peremouan
        for(int i = 0 ;i < dataMasiswa.size();i++){

            System.out.println((i+1)+"\t"+dataMasiswa.get(i).nim+"\t"+dataMasiswa.get(i).name+"\t"+dataMasiswa.get(i).jurusan+"\t"+dataMasiswa.get(i).tahun_lahir+"\t\t"+dataMasiswa.get(i).Jenis_Kelamin);

            if(dataMasiswa.get(i).Jenis_Kelamin.equals("Laki-laki")){
                mahasiswa_laki++;
            }
            else{
                mahasiswa_perempuan++;
            }

            if(dataMasiswa.get(i).jurusan.equals("Teknik Informatika")){
                mahasiswa_ti++;
            }
            else if(dataMasiswa.get(i).jurusan.equals("Sistem Informasi")){
                mahasiswa_si++;
            }
            else{
                mahasiswa_dkv++;
            }
        }


        System.out.println("=====================================================================================================");
        System.out.println("\n\nJumlah Mahasiswa : "+dataMasiswa.size());
        System.out.println("Jumlah mahasiswa Laki laki : " + mahasiswa_laki);
        System.out.println("Jumlah mahasiswa Perempuan : " + mahasiswa_perempuan);
        System.out.println("Jumlah mahasiswa Teknik Informatika : " + mahasiswa_ti);
        System.out.println("Jumlah mahasiswa Sistem Informasi : " + mahasiswa_si);
        System.out.println("Jumlah mahasiswa DKV : " + mahasiswa_dkv);



    }
}
