# 17.04.2019-lab8
###kaplumbaga classı
import java.util.Random;

public class Kaplumbaga {
    int position=0;

    public int getPosition() {
        return position;
    }
    public void hareket_et(){
        int adim=(int)(Math.random()*10+1);
        System.out.println("adim..:"+adim);
        if (adim>=1 && adim <=5){
            konum_guncelle(3);
        }else if (adim>=6 && adim <=7){
            konum_guncelle(-6);
        }else if (adim>=7 && adim <=10){
            konum_guncelle(1);
        }
        System.out.println("K konum..:"+position);
    }
    public void konum_guncelle(int adim){
        if (position+adim<0){
            position=0;
        }else if (position+adim>70){
            position=70;
        }else {
            position+=position;
        }
    }
}

###Tavsan Classı
import java.util.Random;

public class Tavsan {
    int position=0;

    public int getPosition() {
        return position;
    }


    public void hareket_et(){
        int adim=(int)(Math.random()*10+1);
        System.out.println("adim..:"+adim);
        if (adim>=1 && adim <=2){
            System.out.println("Sleep");
        }else if (adim>=3 && adim <=4){
            position+=9;
        }else if(adim==5){
            if (position-12<0)
                position=0;
            else
                position-=12;
        }else if (adim>=6 && adim <=8){
           position+=1;
        }else if (adim>=9 && adim <=10){
            if (position-2<0)
                position=0;
            else
                position-=2;
        }

        System.out.println("T konum..:"+position);
    }
}
###Main Classı

public class Main {
   public static void main(String[] args){
    Kaplumbaga K=new Kaplumbaga();
    Tavsan T=new Tavsan();
    String[] yol=new String[70];
    boolean kazanan=false;
    while (!kazanan){
        K.hareket_et();
        T.hareket_et();
        System.out.println("Yarışma devam ediyor...");
        if (K.getPosition()>=10 && T.getPosition()>=10){
            System.out.println("Berabere bitti ...");
            kazanan=true;
        }else if(K.getPosition()>=10){
            System.out.println("Kaplumbağa Kazandı ...");
            kazanan=true;
        }else if (T.getPosition()>=10){
            System.out.println("Tavşan Kazandı ...");
            kazanan=true;
        }
    }
   }
}
