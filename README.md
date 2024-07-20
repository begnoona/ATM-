import java.util.Scanner;


public class Main {

    public static void main(String[] args) {
    
        String userName,password;
        int login=3;
        int select;
        int balance=3000;
        int money;
        Scanner input=new Scanner(System.in);

       while(login>0){
           System.out.print("Lütfen kullanıcı adınızı giriniz: ");
           userName=input.nextLine();
           System.out.print("Lütfen şifrenizi giriniz: ");
           password=input.nextLine();

           if(userName.equals("Begnoona") && password.equals("Yazilimci123")){
               System.out.println("Yazılımcı Bankasına Hoşgeldiniz!");
               do{
                   System.out.println("1-Para Yatırma\n" +
                           "2-Para Çekme\n" +
                           "3-Bakiye Sorgulama\n" +
                           "4-Çıkış Yap\n");
                   System.out.print("Lütfen yapmak istediğiniz işlemi seçiniz: ");
                   select=input.nextInt();
                   switch(select){
                       case 1:
                           System.out.print("Yatırmak istediğiniz para miktarı: ");
                           money=input.nextInt();
                           balance+=money;
                           System.out.println("Yeni Para miktarı: "+balance);
                           break;
                       case 2:
                           System.out.print("Çekmek istediğiniz miktarı giriniz: ");
                           money=input.nextInt();
                           if(money>balance){
                               System.out.println("Yetersiz Bakiye!");
                           }else{
                               balance-=money;

                           }
                           System.out.println("Yeni Para Miktarı: " +balance);
                           break;
                       case 3:
                           System.out.println("Para Miktarınız: "+balance);
                           break;
                       default:
                           System.out.print("Yanlış tercih yaptınız tekrar deneyiniz!");
                   }


               }while(select!=4);
               System.out.println("Tekrar görüşmek üzere!");
           }
           else{
               --login;
               System.out.println("Hatalı kullanıcı adı veya şifre tekrar deneyiniz: ");
               if(login==0){
                   System.out.println("Hesabınız bloke olmuştur lütfen bankamızla iletişime geçiniz");

               }
               else{
                   System.out.println("Kalan Hakkınız: "+login);
               }
           }

       }



    }
}
