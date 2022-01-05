public int solution(int N, string S) {
   int number = 1;
   int counter = 0;
   List listReserved = new List();
   listReserved = S.Split(' ').ToList();
   while (number <= N) {
      if (listReserved.Where(x => x.Contains(number + "B") || x.Contains(number + "C") || x.Contains(number + "D") || x.Contains(number + "E")).FirstOrDefault() == null) {
         listReserved.AddRange(new List {
            number + "B", number + "C", number + "D", number + "E"
         });
         counter++;
      }

      if (listReserved.Where(x => x.Contains(number + "F") || x.Contains(number + "G") || x.Contains(number + "H") || x.Contains(number + "J")).FirstOrDefault() == null) {
         listReserved.AddRange(new List {
            number + "F", number + "G", number + "H", number + "J"
         });
         counter++;
      }

      if (listReserved.Where(x => x.Contains(number + "D") || x.Contains(number + "E") || x.Contains(number + "F") || x.Contains(number + "G")).FirstOrDefault() == null) {
         listReserved.AddRange(new List {
            number + "D", number + "E", number + "F", number + "G"
         });
         counter++;
      }

      number++;
   }

   return counter;
}
