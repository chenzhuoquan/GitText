//这里添加了一行注释
package Git;

import java.util.Scanner;

public class GitText {


    public static char[] encryptFirst(char []nums){


        for(int i=0;i<nums.length;i++){
            int j=(int)nums[i];//每个字符转化为ASCII值
            int j1=j+i+1+3;//将转化之后的值加上在字符串中的位置和3
            if(j1>127){
                j1-=127;
            }
            nums[i]=(char)j1;
        }
        return nums;
    }
    public static char[] encryptSecond(char[] nums2){
        char i=' ';
        int length=nums2.length;
        i=nums2[0];
        nums2[0]=nums2[length-1];
        nums2[length-1]=i;
        return nums2;
    }
    public static boolean judgeNum(char[]nums3){
        boolean flag=true;
        for(char i:nums3){
            if(!((int)i>=48&&(int)i<=57)){
                flag=false;
            }
        }
        return flag;
    }
    public static boolean judgeChar(char[]nums4){
        boolean flag=true;
        for(char i:nums4){
            if(!((int)i>=65&&(int)i<=122)){
                flag=false;
            }
        }
        return flag;
    }
    public static boolean judgeNum1(char[]nums4){
        for(char i:nums4){
            if(((int)i>=48&&(int)i<=57)){
                return true;
            }
        }
        return false;
    }
    public static boolean judgeChar1(char[]nums4){
        for(char i:nums4){
            if(((int)i>=65&&(int)i<=122)){
                return true;
            }
        }
        return false;
    }
    public static boolean judgeBChar(char[]nums4){
        for(char i:nums4){
            if(((int)i>=65&&(int)i<=90)){
                return true;
            }
        }
        return false;
    }
    public static boolean judgeSChar(char[]nums4){
        for(char i:nums4){
            if(((int)i>=97&&(int)i<=122)){
                return true;
            }
        }
        return false;

    }
    public static void menu(){
        System.out.println("===========================");
        System.out.println("      欢迎使用密码管理系统     ");
        System.out.println("===========================");
        System.out.println("         请选择操作:         ");
        System.out.println("     1.加密     2.解密      ");
        System.out.println("       3.判断密码强度        ");
        System.out.println("     4.密码生成  5.退出      ");
    }



    public static void  main(String[] args) {

        int input=0;
        do{
            menu();
            Scanner scanner=new Scanner(System.in);
            System.out.print("请输入选项序号:");
            input=scanner.nextInt();
            switch (input){
                case 1: System.out.println("===========================");
                        System.out.println("      欢迎使用密码管理系统     ");
                        System.out.println("===========================");
                        System.out.print("请输入要加密的数字密码:");
                        Scanner scanner1=new Scanner(System.in);
                        String s = scanner1.nextLine();
                        char[] chars1 = encryptSecond(encryptFirst( s.toCharArray()));
                        String s2 = String.valueOf(chars1);
                        StringBuffer stringBuffer=new StringBuffer(s2);
                        String s3 = stringBuffer.reverse().toString();
                        System.out.println("加密后的结果是:"+s3);
                        break;


                case 2: System.out.println("===========================");
                        System.out.println("      欢迎使用密码管理系统     ");
                        System.out.println("===========================");
                        System.out.print("请输入要解密的数字密码:");
                        Scanner scanner2=new Scanner(System.in);
                        String s1 = scanner2.nextLine();
                        StringBuffer stringBuffer1=new StringBuffer(s1);
                        String s4 = stringBuffer1.reverse().toString();
                        char[] chars5 = encryptFirst(encryptSecond(s4.toCharArray()));
                        String s5 = String.valueOf(chars5);
                        System.out.println("解密后的结果是:"+s5);
                        break;
            }

        }while(input!=5);


/*        String s="55gdgd89";
        char[]s1=new char[s.length()];
        for (int i=0;i<s.length();i++){
            s1[i]=s.charAt(i);
        }
        encryptFirst(s1);
        encryptSecond(s1);

        String s2 = String.valueOf(s1);
        StringBuffer stringBuffer=new StringBuffer(s2);
        String s3 = stringBuffer.reverse().toString();
        System.out.println(s3);*/
      /*  if(s1.length<8){
            System.out.println("small，长度小于8");
        }else if(judgeNum(s1)||judgeChar(s1)){
            System.out.println("small，length >8 and only one type长度大于8并且只有一种字符类型");
        }else if((judgeNum1(s1)&&judgeBChar(s1)&&judgeSChar(s1))){
            System.out.println("height,ai least one num and small char and big char至少有一个数字、一个小写字母、一个大写字母");
        }
        else if((judgeNum1(s1)&&judgeChar1(s1))){
            System.out.println("middle，only one sum and char有一个数字和一个字母");
        }*/



    }

}
