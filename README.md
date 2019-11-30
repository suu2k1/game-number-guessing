import java.util.Random;
import java.util.Scanner;

public class bai_5 {

    public static void main(String[] args) {
        int[] remember = new int[100000];
        Random random = new Random();
        int key = random.nextInt(101);
        System.out.println(key);
        System.out.println("Nhập một số trong khoảng từ 0 đến 100:");
        int count = 0;

        while (true){
            Scanner scanner1 = new Scanner(System.in);
            int x = scanner1.nextInt();
            count ++;
            remember[count] = x;
            if (x < 0) {
                System.out.println("Bạn đã nhập số ngoài vùng (nhỏ hơn 0)");
                System.out.println("Nhập lại:");
                continue;
            }
            if (x > 100) {
                System.out.println("Bạn đã nhập số ngoài vùng (lớn hơn 100)");
                System.out.println("Nhập lại:");
                continue;
            }
            if (x == key) {
                System.out.println("Bạn đã đoán trúng");
                break;
            }
            if (x > key) {
                System.out.println("Số bạn đoán lớn hơn số cần đoán");
                System.out.println("Nhập lại:");
                continue;
            }
            if (x < key) {
                System.out.println("Số bạn đoán nhỏ hơn số cần đoán");
                System.out.println("Nhập lại:");
                continue;
            }

        }
        System.out.println("Bạn đã đoán " + count + " lần, cụ thể như sau:");
        for (int i = 1; i <= count ; i++) {
            System.out.println("Lần " + i + ": " + remember[i]);
        }
        System.out.println("End game!!!");
    }
}
