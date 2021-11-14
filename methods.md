# methods


package com.company;

public class Main {

    public static void main(String[] args) {
        // 1) Принимает двумерный (квадратный) массив интов, возвращает сумму диалогалей
        int[][] array = new int[][] {{4,7,8},{3,5,2},{8,5,3}};
        sumDiag(array);

        // 2. Принимает двумерный массив long и двумерный массив булеан, возвращает одномерный массив лонгов который состоит из элементов первого массива. По индексам по которым в массиве булеан хранятся значения тру.
        long[][] longs = new long[][] {{4,8,2},{5,9,2},{4,7,4}};
        boolean [][] bool = new boolean[][] {{true, false, true}, {false, true, true}, {true, true, false}};

        long res[] = change(longs, bool);
        for (long value: res){
            System.out.format("%d ", value);
        } System.out.println(" ");
        System.out.println("-----------------");


        // 3. Принимает двумерный массив символов - выводит его на экран.
        char[][] chars = new char[][] {{'a','b','c'},{'y','u','s'}};
        printChars(chars);
    }





    // 1) Принимает двумерный (квадратный) массив интов, возвращает сумму диалогалей
    public static void sumDiag(int array[][]) {
        int sum = 0;
        for(int i=0;i<array.length;i++){
            sum+=array[i][i] + array[i][array.length-1-i];
        }
        System.out.println(sum);
        System.out.println("-----------------");
    }


    // 2. Принимает двумерный массив long и двумерный массив булеан, возвращает одномерный массив лонгов который состоит из элементов первого массива. По индексам по которым в массиве булеан хранятся значения тру.
    public static long[] change(long[][] longs, boolean [][] bool){
        int count = 0;
        for(int i = 0; i < bool.length; i++){
            for (int j = 0; j < bool[i].length; j++){
                if(bool[i][j]){
                    count++;
                }
            }
        }

        int ind = 0;
        long[] res = new long[count];
        for(int i = 0; i < bool.length; i++){
            for (int j = 0; j < bool[i].length; j++){
                if(bool[i][j]){
                    res[ind] = longs[i][j];
                    ind++;
                }
            }
        }
        return res;
    }


    // 3. Принимает двумерный массив символов - выводит его на экран.
    public static void printChars(char[][] chars){
        for(int i = 0; i < chars.length; i++){
            for (int j = 0; j < chars[i].length; j++){
                System.out.print(chars[i][j] + " ");
            }
            System.out.println(" ");
        }
        System.out.println("-----------------");
    }
}
