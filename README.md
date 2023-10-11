# Building Recommender System
Terdapat 2 dasar tipe sistem rekomendasi:

1. Sistem Rekomendasi Sederhana
2. Sistem Rekomendasi Berdasarkan Konten dari Fiturnya
 
Sistem Rekomendasi Sederhana, adalah sistem rekomendasi yang hanya menggunakan urutan sebagai dasar perhitungannya, yang biasanya digunakan dalam '5 film terbaik' kita akan menggunakan urutan berdasarkan mungkin vote terbanyak, rating tertinggi, penjualan film paling tinggi, atau apapun yang lain.
Dalam kasus ini, kita akan menggunakan kombinasi antara rata-rata rating, jumlah vote, dan membentuk metric baru dari metric yang sudah ada, kemudian kita akan melakukan sorting untuk metric ini dari yang tertinggi ke terendah.

# Simple Recommender Engine using Weighted Average
Simple Recommender Engine menawarkan rekomendasi yang umum untuk semua user berdasarkan popularitas film dan terkadang genre.

Ide awal di balik sistem rekomendasi ini adalah sebagai berikut.

Film-film yang lebih populer akan memiliki kemungkinan yang lebih besar untuk disukai juga oleh rata-rata penonton.
Model ini tidak memberikan rekomendasi yang personal untuk setiap tipe user. 
Implementasi model ini pun juga bisa dibilang cukup mudah, yang perlu kita lakukan hanyalah mengurutkan film-film tersebut berdasarkan rating dan popularitas dan menunjukkan film teratas dari list film tersebut.
Sebagai tambahan, kita dapat menambahkan genre untuk mendapatkan film teratas untuk genre spesifik tersebut

Formula dari IMDB dengan Weighted Rating
 
Weighted Rating (WR) = (v/v+m).R + (m?v+m).C

dimana,
v: jumlah votes untuk film tersebut 

m: jumlah minimum votes yang dibutuhkan supaya dapat masuk dalam chart

R: rata-rata rating dari film tersebut

C: rata-rata jumlah votes dari seluruh semesta film

# Building Recommender System with Similarity Function

Recommender system yang menggunakan Content/feature dari film/entitas tersebut, kemudian melakukan perhitungan terhadap kesamaannya satu dan yang lain sehingga ketika kita menunjuk ke satu film, kita akan mendapat beberapa film lain yang memiliki kesamaan dengan film tersebut. Hal ini biasa kita sebut sebagai Content Based Recommender System.

Dengan membandingkan kesamaan plot yang ada dan genre yang ada, ketika audience lebih menyukai film Narnia, maka content based recommender system ini akan juga merekomendasikan film seperti Harry Potter atau The Lords of The Rings yang memiliki genre yang mirip
