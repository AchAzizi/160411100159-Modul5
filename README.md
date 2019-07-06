# Modul-5
# Rangkuman-Modul5

Recursif
Rekursif ini sebenarnya merupakan sebuah perulangan di dalam sebuah program
namun, perulangan ini sangat berbeda dengan perulangan pada umumnya
seperti while dan for, Walaupun fungsinya sama yaitu perulangan atau looping.
Letak perbedaannya adalah dari cara kerjanya, jika for dan while merupakan sebuah perulangan yang menggunakan sebuah kondisi atau boolean,
maka pada rekursif ini terjadi pada sebuah fungsi atau metode yang memanggil dirinya sendiri.

Iteratif
merupakan penyelesaian permasalahan dengan perulangan, menggunakan syntax for atau while (pada Python). 

Pada code ini, terdapat iterasi while, yang menghitung perkalian, mulai dari nn, sampai dengan 2.
Contoh kode:

      def factorialIteratif(bilangan):
          if bilangan <=1:
              return(1)
          else:
              temp=bilangan
              hasil=1
              while temp>1:
                  hasil=hasil*temp
                  temp=temp-1
              return(hasil)
              
      print(factorialIteratif(4))
24


Berikut adalah code untuk perhitungan faktorial dengan cara rekursif

      def factorialRekursif(bilangan):
          if bilangan <=1:
              return(1)
          else:
              return(bilangan * factorialRekursif(bilangan-1))
              
      data=factorialRekursif(4)
      print(data)
24

Dari fungsi tersebut dapat dilihat bahwa teknik pemrograman rekursif ini melibatkan pemanggilan fungsinya itu sendiri dengan argument
atau parameter yang berukuran lebih kecil. Berikut beberapa aturan dalam teknik pemrograman rekursif:
  1. Fungsi rekursif harus memiliki base case, base case inilah yang berfungsi untuk menghentikan pemanggilan terus menerus fungsi
     rekursif
  2. fungsi rekursif harus memiliki sintaks yang dapat merubah state dari permasalahan, sehingga semakin lama solusi permasalahan
     menuju base case yang sudah dibuat
  3. Fungsi rekursif harus memanggil dirinya sendiri
  
  
Implementasi Rekursif
Banyak permasalahan yang dapat diselesaikan dengan teknik pemrograman rekursif ini, berikut saya lampirkan contoh 
kode programnya:

code untuk menghitung triangular numbers melalui teknik iteratif

      def triangularNumbers1(n):
          total=0
          temp=n
          while temp>=1:
              total+=temp
              temp-=1
          return(total)
          
      print(triangularNumbers1(2))
  3


Untuk mencari deret ke-nn dari triangular numbers, dapat juga digunakan fungsi rekursif seperti permasalahan perhitungan faktorial
sebelumnya. Base case dari triangular numbers ini adalah ketika deret ke-1 yang bernilai 1.
Berikut fungsi rekursif dari triangular numbers.

      def triangularNumbers2(n):
          if n==1:
              return(1)
          else:
              return (n + triangularNumbrs2(n-1))
              
print(triangularNumbers1(8))



Konversi Bilangan
suatu proses dimana satu system bilangan dengan basis tertentu akan dijadikan bilangan dengan basis yang lain.
Bilangan integer ini dikenal juga sebagai bilangan dengan base 10 (desimal), sehingga memiliki kemungkinan character angka dari 0 s.d 9.

Berikut fungsi rekursif untuk konversi bilangan desimal menjadi bilangan base yang lain.

            def konversiDesimal(bilangan,base):
                charBilangan='0123456789ABCDEF'
                if bilangan<base:
                    return(charBilangan[bilangan])
                else:
                    temp=bilangan//base
                    ind=bilangan % base
                    print(type(temp),temp,type(ind),ind)
                    return(konversiDesimal(temp,base)+charBilangan[ind])
                    
            konversiDesimal(5,2)
            



Towers of Hanoi
ini diinspirasi oleh cerita mitos dari sebuah kuil di India. Pada saat itu, pendeta memerintahkan para pekerjanya atau pendeta muda untuk memindahkan 64 piringan emas dengan ukuran yang berbeda-beda dari satu tiang ke tiang lainnya.
Syarat memindahkan piringan emas ini adalah :
      1. piringan emas harus dipindahkan satu persatu
      2. piringan emas berukuran kecil harus berada diatas piringan emas berukuran besar.

Berikut algoritma untuk memindahkan piringan sebanyak nn, dari tiang awal ke tiang tujuan, melalui suatu tiang bantuan:
      1. pindahkan piringan sebanyak n-1n−1 dari tiang awal ke tiang bantuan, melalui tiang tujuan
      2. pindahkan piringan ke nn dari tiang awal ke tiang tujuan
      3. pindahkan piringan sebanyak n-1n−1 dari tiang bantuan ke tiang tujuan, melalui tiang awal
      
Berikut code untuk penyelesaian permasalahan towers of hanoi dengan menggunakan teknik rekursif

            def towers(n,awal,bantuan,tujuan):
                if n==1:
                    print("Piringan - 1 dari-", awal,"ke-",tujuan)
                else:
                    towers(n-1,awal,tujuan,bantuan)
                    print("Piringan -",n, "dari-",awal,"ke-", tujuan)
                    towers(n-1,bantuan,awal,tujuan
                    
            towers(4,'A','B','C')
            
            
            
Visualisasi Teknik Pemrograman Rekursif
Berikut adalah pembuatan bentuk spiral secara rekursif dengan menggunakan modul Turtle

            import turtle
            my_turtle = turtle.Turtle()
            my_win = turtle.Screen()

            def draw_spiral(my_turtle, line_len):
                if line_len > 0:
                    my_turtle.forward(line_len)
                    my_turtle.right(90)
                    draw_spiral(my_turtle, line_len - 5)

            draw_spiral(my_turtle, 90)
            my_win.exitonclick()
            
            
 ......................................................................................................................................           
            Mohon Maaf bu, untuk Praktikum Modul-5 (File Tugas Praktikum saya sertakan di lampiran)
            di karena saya tidak bisa untuk memasukkan gambar kedalam halaman

 ......................................................................................................................................

#Jawaban Praktikum 

                        import turtle
                        def tree(branch_len, t):
                            t.speed('slowest')
                            if branch_len > 5:
                                t.forward(branch_len)
                                t.right(20)
                                tree(branch_len - 15, t)
                                t.left(40)
                                tree(branch_len - 15, t)
                                t.right(20)
                                t.backward(branch_len)

                        def main():
                            my_win = turtle.Screen()
                            t = turtle.Turtle()

                            t.shape("turtle")
                            t.left(90)
                            t.up()
                            t.backward(100)
                            t.down()
                            t.color("green")
                            tree(60, t)
                            my_win.exitonclick()
                        main()

            Segitia Sierpinski ini juga merupakan bentuk fraktal. Segitiga ini memiliki bentuk dasar (yaitu, suatu segitiga dan didalamnya terdapat empat buat segitiga dengan ukuran yang sama), dan bentuk dasar ini terus menerus dibangkitkan sampai derajat tertentu.

            Berikut contoh code untuk pembuatan Segitiga Sierpinski:

            import turtle
            def draw_triangle(points, color, my_turtle):   
                my_turtle.speed('slowest')
                my_turtle.fillcolor(color)
                my_turtle.up()
                my_turtle.goto(points[0][0],points[0][1])
                my_turtle.down()
                my_turtle.begin_fill()
                my_turtle.goto(points[1][0], points[1][1])
                my_turtle.goto(points[2][0], points[2][1])
                my_turtle.goto(points[0][0], points[0][1])
                my_turtle.end_fill()
            def get_mid(p1, p2):
                return ((p1[0] + p2[0]) / 2, (p1[1] + p2[1]) / 2)
            def sierpinski(points, degree, my_turtle):
                color_map = ["blue", "red" , "green", "white" , "yellow" ,"violet" , "orange"]
                draw_triangle(points, color_map[degree], my_turtle)
                if degree > 0:
                    sierpinski([points[0],get_mid(points[0], points[1]), get_mid(points[0], points[2])], degree-1, my_turtle)
                    sierpinski([points[1],get_mid(points[0], points[1]), get_mid(points[1], points[2])], degree-1, my_turtle)
                    sierpinski([points[2],get_mid(points[2], points[1]), get_mid(points[0], points[2])], degree-1, my_turtle)

            def main():
                my_turtle = turtle.Turtle()
                my_win = turtle.Screen()
                my_points = [[-100, -50], [0, 100], [100, -50]]
                sierpinski(my_points, 2, my_turtle)
                my_win.exitonclick()

            main()
