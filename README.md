 /**
     * @param N: the number of rows
     * @param S: a list of reserved seats
     * @return: An integer
     */
    public int solution(int N, String S) {
        // Write your code here.
        int[][] seats = new int[N][10];

        if(!S.equals("")) {
            String[] used = S.split(" ");
            System.out.println(used.length);
            for(int i=0; i<used.length; i++){
                int line = Integer.parseInt(used[i].substring(0,used[i].length()-1))-1;
                //System.out.println(used[i].charAt(1));
                int num = (int)used[i].charAt(used[i].length()-1)-65;
                System.out.println(line + "-" +num);
                seats[line][num] = 1;
            }
        }
        

        int result = 0;
        for(int i=0; i<N; i++){
            if(seats[i][1] + seats[i][2] + seats[i][3] + seats[i][4] == 0){
                result++;
                seats[i][1] = 1;
                seats[i][2] = 1;
                seats[i][3] = 1;
                seats[i][4] = 1;
            }
            if(seats[i][3] + seats[i][4] + seats[i][5] + seats[i][6] == 0){
                result++;
                seats[i][3] = 1;
                seats[i][4] = 1;
                seats[i][5] = 1;
                seats[i][6] = 1;
            }
            if(seats[i][5] + seats[i][6] + seats[i][7] + seats[i][8] == 0){
                result++;
                seats[i][5] = 1;
                seats[i][6] = 1;
                seats[i][7] = 1;
                seats[i][8] = 1;
            }
        }
        return result;
    }
}
