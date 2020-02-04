# README(paiza_learning_1_Java)
# 概要
本ファイルは、学習中のpaizaラーニング「Java 入門編」の履修内容を一部紹介するために作成した。目次や一部カリキュラム（それぞれのチャプターの最初の２つ）は、ログインしていなくても見ることができる。演習問題のコード中の注釈は、私が書いたもの。  
【目次のページ】  
https://paiza.jp/works/java/primer
![スクリーンショット 2020-02-01 14 15 39](https://user-images.githubusercontent.com/56028886/73587274-7cd57500-44fd-11ea-9e49-2423722c7f5c.png)  
## カリキュラム一覧
Java入門編1:プログラミングを学ぶ (全9回)  
Javaでプログラミングの初歩を学びます。第一回では変数と計算について学びます。  
「サイコロ」Webアプリを作れるようになる事を目指します。  
  
Java入門編2:条件によって処理を変えてみよう (全11回)  
Javaでプログラミングの初歩を学びます。「平成年度の計算」や「おみくじ」など、簡単なWebアプリケーションを作れるようになる事を目指します。  
  
Java入門編3: ループ処理を学ぶ (全9回)  
Javaを使って、同じ手順を繰り返すループ処理の基本を学びます。ループ処理は、大量のデータを処理するためには、欠かせないテクニックです。また今回は、プログラムの外部からデータを入力する方法についても取り上げます。  
  
Java入門編4:配列の基礎 (全9回)  
大規模なデータを扱うプログラムを作るときに必要になる配列について学びます。  
【＃06:ArrayListクラスを使おう】演習問題_3&4
```
import java.util.*;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> weapon = new ArrayList<String>();
        weapon.add("木の棒");
        weapon.add("鉄の棒");
        weapon.add("鉄の剣");
        weapon.add("銅の剣");
        weapon.remove(2);  //要素を加える場合は、set(index,"要素名")
        for (String item : weapon) {
            System.out.println(item.size());
        }
    }
}
```
```
出力//
3
```
  
Bランクレベルアップセット  
  
Java入門編5: 2次元配列を理解しよう (全11回)  
Javaでの2次元配列の基礎について学び、配列のループ処理について理解を深めます。  
【07:3次元配列で複数のドット絵を表示する】演習問題_1  
```  
public class Main {
    public static void main(String[] args) {

        int[][][] letters =
            {{{0,0,1,1,0,0},
             {0,1,0,0,1,0},
             {1,0,0,0,0,1},
             {1,1,1,1,1,1},
             {1,0,0,0,0,1},
             {1,0,0,0,0,1}},
            {{1,1,1,1,1,0},
             {1,0,0,0,0,1},
             {1,1,1,1,1,0},
             {1,0,0,0,0,1},
             {1,0,0,0,0,1},
             {1,1,1,1,1,0}},
            {{0,1,1,1,1,0},
             {1,0,0,0,0,1},
             {1,0,0,0,0,0},
             {1,0,0,0,0,0},
             {1,0,0,0,0,1},
             {0,1,1,1,1,0}}};
    //大外の配列  
    for (int[][] image : letters) {  
        //外の配列  
        for(int[] line: image) {  
            //最内の配列  
            for (int dot : line) {  
                if (dot == 1) {
                    System.out.print("@");
                } else {
                    System.out.print(" ");
                }
            }
            //最内の配列の改行（これが無いと一列にならない）  
            System.out.println("");
        }
        //外の配列の改行（これが無いとimgがくっついてしまう）
        System.out.println("");
        }
    }
}
```
```
//出力
 @@  
 @  @
@    @
@@@@@@
@    @
@    @

@@@@@
@    @
@@@@@
@    @
@    @
@@@@@

 @@@@
@    @
@     
@     
@    @
 @@@@  
```
【#09:2次元配列で地図を表示する２】演習問題_1  
```
public class Main {
    public static void main(String[] args) {
        //二次元配列の初期値を設定（5行と10列）
        String[][] areaMap = new String[5][10];
        //外側のループ（行）
        for (int i = 0; i < areaMap.length; i++) {
            //内側のループ（列）  
            for (int j = 0; j < areaMap[i].length; j++) {
                if (i % 2 == 0 && j % 2 == 0){
                areaMap[i][j] = "+";
                }else{
                areaMap[i][j] = ".";  
                }
                System.out.print(areaMap[i][j]);
            }
            //行ごとに改行  
            System.out.println("");
        }
    }
}
```
```
//出力
+.+.+.+.+.
..........
+.+.+.+.+.
..........
+.+.+.+.+.
```
Java入門編6: メソッドを理解しよう (全6回)  
Javaのメソッドについて、その呼び出し方や作り方など、基本機能を学習します。  
【＃03:引数と戻り値を追加しよう】演習問題（「九九の表を作成してみよう」）  
```
public class Main {
    public static void main(String[] args) {
        for (int num1 = 1; num1 <= 9; num1++) {   
            for (int num2 = 1; num2 <= 9; num2++) {
            //下段に記述されたメソッドを使用して出力。
            System.out.print(multi(num1, num2));
            //数値と数値の間のコンマの処理
            if (num2 < 9) {
                System.out.print(", ");
            } else {
               //*9で改行。
                System.out.println("");
            }
        }
    }
}
    public static int multi(int x, int y) {
        //返り値の記述
        return x * y;
    }
}
```
```
//出力  
1, 2, 3, 4, 5, 6, 7, 8, 9
2, 4, 6, 8, 10, 12, 14, 16, 18
3, 6, 9, 12, 15, 18, 21, 24, 27
4, 8, 12, 16, 20, 24, 28, 32, 36
5, 10, 15, 20, 25, 30, 35, 40, 45
6, 12, 18, 24, 30, 36, 42, 48, 54
7, 14, 21, 28, 35, 42, 49, 56, 63
8, 16, 24, 32, 40, 48, 56, 64, 72
9, 18, 27, 36, 45, 54, 63, 72, 81
```  
【＃05:RPGの攻撃シーンを作ろう】演習問題_1  
```
public class Main {
    public static void main(String[] args) {
        String[] team = {"勇者", "戦士", "魔法使い"};
        //デフォルトの体力（300）を定義。これはインスタンスフィールド。
        int enemy_hp = 300;
        for (String person : team) {
            // 敵の体力を減少させるコード。下段で定義されたattackメソッドを呼ぶ。引数は1行上のperson。  
            enemy_hp = enemy_hp - attack(person);
            System.out.println("敵のHPは残り" + enemy_hp + "です");
        }
    }
   //クラスメソッドはstaticを付ける。これでMainクラスの中で全般的に利用できるようになる。
     static を消すと、参照できないというエラーが出る。また、ここではメソッドだけが定義されている。
     変数player の名称は何でも良い。
   public static int attack(String player) {  
        System.out.println(player + "はスライムを攻撃した");
        int hit = (int) (Math.random() * 10 + 1) * 10;
        System.out.println(hit + "のダメージを与えた");
        return hit;ⅻ
    }
}
```
```
//出力(randomメソッドを用いているため、数値は実行の都度異なります)
勇者はスライムを攻撃した
30のダメージを与えた
敵のHPは残り270です
戦士はスライムを攻撃した
50のダメージを与えた
敵のHPは残り250です
魔法使いはスライムを攻撃した
20のダメージを与えた
敵のHPは残り280です
```

Bランクレベルアップセット  
  
Java入門編7: クラスを理解しよう (全8回)  <= 2月2日時点の学習位置  
Javaのクラスの作り方や使い方など、クラスの基本的な機能について学習します。  

【＃02:クラスを作成しよう】演習問題
```
public class Main {
    public static void main(String[] args) {
        //下段で定義したクラスから新しいオブジェクトを生成。
        Greeting greet = new Greeting();
       //greet という名の変数をつくって、そこへ代入。
        greet.sayHello();                                
    }
}
class Greeting {
    //sayHelloメソッドの定義。型の定義は不要。
    public void sayHello() {                     
        System.out.println("hello paiza");
    }
}
```
```
//出力
hello paiza
```
【#03:変数をクラスで管理しよう】演習問題_１ 
```
public class Main {
    public static void main(String[] args) {
        //Greetingクラスから新しいインスタンス（"paiza"）を生成。
        Greeting greet = new Greeting("paiza");
        greet.sayHello();
    }
}

class Greeting {
    private String myName;　//myNameという変数を作る。parivateにすることで、クラスがインスタンス化されることを防ぐ（※）。
　　//以下でこの変数を初期化 = コンストラクタ　
    public Greeting(String n) {
        myName = n;
    }
    public void sayHello() {
        System.out.println("hello " + myName);
    }
}
```
Java入門編8:さらにクラスを理解しよう (全8回)  
クラス継承やメソッドのオーバーライドなど、Javaのオブジェクト指向開発についてさらに学習します。  
  
Java入門編9: HashMap(連想配列)の基礎 (全6回)  
JavaでのHashMap(連想配列)の基礎について学び、RPGのアイテム一覧を作る事を目指します。  
  
Java入門編10:例外処理を理解しよう (全13回)  
実行時に発生したエラーに対応する、Javaの例外処理について学習します。  
  
以上です。  
