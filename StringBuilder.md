# C# Tips & Tricks [ต่อ StringBuilder เร็วกว่า]
  
โดยปกติเรามักต่อข้อความในตัวแปร String  ใช้ในกรณีที่เราต้องการเก็บข้อความที่ม เช่นคำสัง SQL หรือ อื่นๆ
สิ่งที่เราทำนั่นไม่ผิดหรอก เพียงแต่มันยังไม่ใช่สิงที่ดี ในกรณีแบบนี้แนะนำให้ใช้ StringBuilder ในการเขียนโปรแกรมดีกว่า
เพราะมันเร็วมากกว่า String ธรรมดาเยอะ ลองทำดูผลลัพธ์จาก Code นี้ 
  
            Stopwatch _sw = new Stopwatch();
            string _string1 = String.Empty;
            _sw.Start();
            for (int i = 0; i < 10000; i++)
            {
                _string1 += i.ToString();
            }
            _sw.Stop();
            Console.WriteLine("[String] Process time : " + _sw.ElapsedMilliseconds + " ms.");

            //String Builder

            Stopwatch _sw1 = new Stopwatch();
            StringBuilder _string2 = new StringBuilder();
            _sw1.Start();
            for (int i = 0; i < 1000000; i++)
            {
                _string2.Append(i.ToString());
            }
            _sw1.Stop();
            Console.WriteLine("[StringBuilder] Process time : " + _sw1.ElapsedMilliseconds + " ms.");
            Console.ReadKey();
