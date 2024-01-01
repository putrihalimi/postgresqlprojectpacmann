# Used Car
## _Perbandingan Penjualan Tahun Sekarang dgn Lalu_

Penjelasan mengenai project yang Saya dibuat :
* ERD
* Syntax DDL
* Dummy dataset
* Transactional Query
* Analytical Query

Saya belum buat ERD nya..
ERD adalah 

Query yang ada pada dataset saya
-- Pemanggilan semua kolom pada tiap tabel 
select * from car_product
select * from city

-- Membuat tabel car_product
CREATE TABLE car_product (
    product_id SERIAL PRIMARY KEY,
    brand VARCHAR,
    model VARCHAR,
    body_type VARCHAR,
    year INTEGER,
    price NUMERIC
);

-- Memasukkan data ke dalam tabel car_product
INSERT INTO car_product (product_id, brand, model, body_type, year, price) VALUES 
(1, 'Toyota', 'Toyota Yaris', 'Hatchback', 2016, 175000000),
(2, 'Toyota', 'Toyota Yaris', 'Hatchback', 2018, 215000000),
(3, 'Toyota', 'Toyota Yaris', 'Hatchback', 2014, 162000000),
(4, 'Toyota', 'Toyota Yaris', 'Hatchback', 2020, 220000000),
(5, 'Toyota', 'Toyota Yaris', 'Hatchback', 2012, 124000000),
(6, 'Toyota', 'Toyota Agya', 'Hatchback', 2019, 114000000),
(7, 'Toyota', 'Toyota Agya', 'Hatchback', 2014, 97000000),
(8, 'Toyota', 'Toyota Agya', 'Hatchback', 2016, 110000000),
(9, 'Toyota', 'Toyota Agya', 'Hatchback', 2022, 155500000),
(10, 'Toyota', 'Toyota Agya', 'Hatchback', 2017, 115500000),
(11, 'Toyota', 'Toyota Calya', 'Wagon', 2019, 130000000),
(12, 'Toyota', 'Toyota Calya', 'Wagon', 2019, 137000000),
(13, 'Toyota', 'Toyota Calya', 'Wagon', 2017, 115500000),
(14, 'Toyota', 'Toyota Calya', 'Wagon', 2016, 104000000),
(15, 'Toyota', 'Toyota Calya', 'Wagon', 2016, 107000000),
(16, 'Daihatsu', 'Daihatsu Ayla', 'Hatchback', 2016, 83000000),
(17, 'Daihatsu', 'Daihatsu Ayla', 'Hatchback', 2019, 120000000),
(18, 'Daihatsu', 'Daihatsu Ayla', 'Hatchback', 2015, 96000000),
(19, 'Daihatsu', 'Daihatsu Ayla', 'Hatchback', 2017, 115000000),
(20, 'Daihatsu', 'Daihatsu Ayla', 'Hatchback', 2017, 113000000),
(21, 'Daihatsu', 'Daihatsu Terios', 'SUV', 2018, 190000000),
(22, 'Daihatsu', 'Daihatsu Terios', 'SUV', 2022, 223000000),
(23, 'Daihatsu', 'Daihatsu Terios', 'SUV', 2019, 189900000),
(24, 'Daihatsu', 'Daihatsu Terios', 'SUV', 2017, 166000000),
(25, 'Daihatsu', 'Daihatsu Terios', 'SUV', 2018, 201000000),
(26, 'Daihatsu', 'Daihatsu Xenia', 'MPV', 2019, 170000000),
(27, 'Daihatsu', 'Daihatsu Xenia', 'MPV', 2022, 220500000),
(28, 'Daihatsu', 'Daihatsu Xenia', 'MPV', 2017, 135000000),
(29, 'Daihatsu', 'Daihatsu Xenia', 'MPV', 2014, 100000000),
(30, 'Daihatsu', 'Daihatsu Xenia', 'MPV', 2018, 159000000),
(31, 'Honda', 'Honda Jazz', 'Hatchback', 2018, 236000000),
(32, 'Honda', 'Honda Jazz', 'Hatchback', 2019, 250000000),
(33, 'Honda', 'Honda Jazz', 'Hatchback', 2018, 216000000),
(34,'Honda', 'Honda Jazz', 'Hatchback', 2015, 192000000),
(35, 'Honda', 'Honda Jazz', 'Hatchback', 2013, 178000000),
(36, 'Honda', 'Honda CR-V', 'SUV', 2018, 415000000),
(37, 'Honda', 'Honda CR-V', 'SUV', 2017, 345000000),
(38, 'Honda', 'Honda CR-V', 'SUV', 2009, 116000000),
(39, 'Honda', 'Honda CR-V', 'SUV', 2016, 269000000),
(40, 'Honda', 'Honda CR-V', 'SUV', 2018, 398500000),
(41, 'Honda', 'Honda Civic', 'Hatchback', 2018, 350000000),
(42, 'Honda', 'Honda Civic', 'Sedan', 2010, 165000000),
(43, 'Honda', 'Honda Civic', 'Sedan', 2013, 186000000),
(44, 'Honda', 'Honda Civic', 'Sedan', 2013, 179000000),
(45, 'Honda', 'Honda Civic', 'Hatchback', 2019, 397500000),
(46, 'Suzuki','Suzuki Ertiga', 'MPV', 2015, 125000000),
(47, 'Suzuki', 'Suzuki Ertiga', 'MPV', 2018, 178000000),
(48, 'Suzuki', 'Suzuki Ertiga',	'MPV', 2016, 168000000),
(49, 'Suzuki', 'Suzuki Ertiga', 'MPV', 2012, 100000000),
(50, 'Suzuki', 'Suzuki Ertiga', 'MPV', 2018, 167000000);

-- Membuat Tabel city
CREATE TABLE city (
    kota_id INT PRIMARY KEY,
    nama_kota VARCHAR(255),
    latitude DECIMAL(9,6),
    longitude DECIMAL(9,6)
);

INSERT INTO city (kota_id, nama_kota, latitude, longitude) VALUES 
(3171, 'Kota Jakarta Pusat', -6.186486, 106.834091),
(3172, 'Kota Jakarta Utara', -6.121435, 106.774124),
(3173, 'Kota Jakarta Barat', -6.1352, 106.813301),
(3174, 'Kota Jakarta Selatan', -6.300641, 106.814095),
(3175, 'Kota Jakarta Timur', -6.264451, 106.895859),
(3573, 'Kota Malang', -7.981894, 112.626503),
(3578, 'Kota Surabaya', -7.289166, 112.734398),
(3471, 'Kota Yogyakarta', -7.797224, 110.368797),
(3273, 'Kota Bandung', -6.914744, 107.609811),
(1371, 'Kota Padang', -0.950000, 100.353056),
(1375, 'Kota Bukittinggi', -0.305556, 100.369167),
(6471, 'Kota Balikpapan', -1.263539, 116.827883),
(6472, 'Kota Samarinda', -0.502183, 117.153801),
(7371, 'Kota Makassar', -5.133333, 119.416667),
(5171, 'Kota Denpasar', -8.656290, 115.222099);

--- Evaluasi Projek Bisnis Mobil Bekas ;
-- Creating Transactional Query

-- mencari mobil keluaran 2015
SELECT product_id, brand, model, year, price FROM car_product WHERE year >= 2015;

-- menambahkan produk mobil baru 
INSERT INTO car_product (product_id, brand, model, body_type, year, price) VALUES (51, 'Toyota', 'Toyota Avanza', 'MPV', 2021, 230000000);

-- akun customer pilih body type terbaru dijual
SELECT product_id, brand, model, body_type, year, date_post
FROM car_product
ORDER BY year DESC;

-- mobil bekas termurah dari pilihan model yang dipilih
SELECT product_id, brand, model, year, price FROM car_product WHERE model LIKE '%Daihatsu%' ORDER BY price ASC;

-- mencari mobil bekas dengan jarak terdekat penjual dan pembeli/distance
SELECT product_id, brand, model, year, price, distance
FROM car_product

--- Creating Analytical Query

-- ranking popularitas model mobil berdasarkan jumlah bid
SELECT
    model,
    COUNT(DISTINCT product_id) AS count_product,
    COUNT(DISTINCT date_bid) AS count_bid
FROM
    car_product
GROUP BY
    model
ORDER BY
    count_bid DESC;

-- membandingkan harga mobil berdasarkan harga rata-rata per kota
SELECT
    city.nama_kota,
    AVG(car_product.price) AS rata_rata_harga
FROM
    car_product
JOIN
    city ON car_product.nama_kota = city.nama_kota
GROUP BY
    city.nama_kota;
	
-- cari perbandingan tanggal user melakukan bid dengan bid selanjutnya beserta harga tawar yang diberikan
SELECT model, user_id, first_bid_date, next_bid_date, first_bid_price, next_bid_price FROM car_product

-- 
-- Menyusun perbandingan rata-rata harga mobil dan harga bid untuk 6 bulan terakhir
WITH ModelAvg AS (
    SELECT
        model,
        AVG(price) AS avg_price
    FROM
        car_product
    GROUP BY
        model
),
BidAvg AS (
    SELECT
        model,
        AVG(bid_price) AS avg_bid_6month
    FROM
        car_product
    WHERE
        date_bid >= CURRENT_DATE - INTERVAL '6 months'
    GROUP BY
        model
)
-- Menggabungkan hasil perhitungan rata-rata harga mobil dan harga bid
SELECT
    ModelAvg.model,
    ModelAvg.avg_price,
    BidAvg.avg_bid_6month,
    ModelAvg.avg_price - BidAvg.avg_bid_6month AS difference,
    ((ModelAvg.avg_price - BidAvg.avg_bid_6month) / ModelAvg.avg_price) * 100 AS difference_percent
FROM
    ModelAvg
JOIN
    BidAvg ON ModelAvg.model = BidAvg.model;

-- Menyusun window function rata-rata harga bid per merk dan model selama 6 bulan terakhir
WITH BidAverages AS (
    SELECT
        brand,
        model,
        bid_price,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 5 PRECEDING AND CURRENT ROW) AS m_min_6,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 4 PRECEDING AND CURRENT ROW) AS m_min_5,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 3 PRECEDING AND CURRENT ROW) AS m_min_4,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS m_min_3,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 1 PRECEDING AND CURRENT ROW) AS m_min_2,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN CURRENT ROW AND CURRENT ROW) AS m_min_1
    FROM
        car_product
    WHERE
        date_bid >= CURRENT_DATE - INTERVAL '6 months'
)
-- Memilih hasil window function untuk contoh merk dan model Toyota Avanza
SELECT
    brand,
    model,
    m_min_6,
    m_min_5,
    m_min_4,
    m_min_3,
    m_min_2,
    m_min_1
FROM
    BidAverages
WHERE
    brand = 'Toyota' AND model = 'Toyota Avanza';

-- -- Menyusun window function rata-rata harga bid per merk dan model selama 6 bulan terakhir
WITH Semua_Brand_Mobil AS (
    SELECT
        brand,
        model,
        bid_price,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 5 PRECEDING AND CURRENT ROW) AS m_min_6,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 4 PRECEDING AND CURRENT ROW) AS m_min_5,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 3 PRECEDING AND CURRENT ROW) AS m_min_4,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS m_min_3,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN 1 PRECEDING AND CURRENT ROW) AS m_min_2,
        AVG(bid_price) OVER (PARTITION BY brand, model ORDER BY date_bid DESC ROWS BETWEEN CURRENT ROW AND CURRENT ROW) AS m_min_1
    FROM
        car_product
    WHERE
        date_bid >= CURRENT_DATE - INTERVAL '6 months'
)
-- Memilih hasil window function untuk semua merk dan model
SELECT DISTINCT
    brand,
    model,
    m_min_6,
    m_min_5,
    m_min_4,
    m_min_3,
    m_min_2,
    m_min_1
FROM
    Semua_Brand_Mobil;







-- Menambahkan kolom user_id ke dalam tabel car_product
ALTER TABLE car_product
ADD COLUMN user_id INTEGER;

-- Mengisi kolom user_id dengan nilai acak antara 1 dan 1000
UPDATE car_product
SET user_id = FLOOR(RANDOM() * 1000) + 1;

-- Menambahkan kolom nama_kota ke dalam tabel car_product
ALTER TABLE car_product
ADD COLUMN nama_kota VARCHAR(255);

-- Memperbarui kolom nama_kota berdasarkan tahun dan kriteria tertentu
UPDATE car_product
SET nama_kota = 'Kota Jakarta Selatan'
WHERE year BETWEEN 2009 AND 2011;

UPDATE car_product
SET nama_kota = 'Kota Balikpapan'
WHERE year BETWEEN 2012 AND 2013 AND year = 2015;

UPDATE car_product
SET nama_kota = 'Kota Denpasar'
WHERE year BETWEEN 2016 AND 2019;

UPDATE car_product
SET nama_kota = 'Kota Samarinda'
WHERE year BETWEEN 2020 AND 2022;

-- menambahkan kolom distance ke dalam tabel car_product
ALTER TABLE car_product
ADD COLUMN distance INTEGER;

-- memasukkan data jarak ke dalam kolom distance berdasarkan tahun mobil
UPDATE car_product SET distance = 10 WHERE year BETWEEN 2012 AND 2016;
UPDATE car_product SET distance = 15 WHERE year BETWEEN 2017 AND 2018;
UPDATE car_product SET distance = 20 WHERE year = 2019;
UPDATE car_product SET distance = 25 WHERE year = 2020;
UPDATE car_product SET distance = 30 WHERE year = 2022;


select * from car_product
---

-- 1. jumlah rank
SELECT model, COUNT(*) as jumlah_mobil, RANK() OVER (ORDER BY COUNT(*) DESC) as peringkat
FROM car_product
GROUP BY model
ORDER BY peringkat;

-- 2. 
SELECT brand, avg(price) as hrg_rata2
from car_product
group by product_id
order by hrg_rata2 desc


-- Menambahkan kolom-kolom baru ke tabel car_product
ALTER TABLE car_product
ADD COLUMN first_bid_date DATE,
ADD COLUMN next_bid_date DATE,
ADD COLUMN first_bid_price INTEGER,
ADD COLUMN next_bid_price INTEGER;

-- Mengisi kolom first_bid_date dengan nilai random dari tahun 2009 sampai 2010
UPDATE car_product SET first_bid_date = DATE '2009-01-01' + INTERVAL '1 year' * (RANDOM() * 2)::INT;

-- Mengisi kolom next_bid_date dengan nilai random dari tahun 2023 sampai 2024
UPDATE car_product SET next_bid_date = DATE '2023-01-01' + INTERVAL '1 year' * (RANDOM() * 2)::INT;

-- Mengisi kolom first_bid_price dengan nilai random
UPDATE car_product SET first_bid_price = FLOOR(RANDOM() * 100000);

-- Mengisi kolom next_bid_price dengan nilai random
UPDATE car_product SET next_bid_price = FLOOR(RANDOM() * 100000);



--
SELECT
    model,
    AVG(price) AS avg_price,
    AVG(bid_price) AS avg_bid_6month,
    (AVG(bid_price) - AVG(price)) AS difference,
    ((AVG(bid_price) - AVG(price)) / AVG(price)) * 100 AS difference_percent,
    (0.04 * ((AVG(bid_price) - AVG(price)) / AVG(price))) AS weighted_difference
FROM
    car_product
WHERE
    sale_date BETWEEN (CURRENT_DATE - INTERVAL '6 months') AND CURRENT_DATE
GROUP BY
    model;



---
-- Menambahkan kolom bid_price ke tabel car_product
ALTER TABLE car_product
ADD COLUMN bid_price INTEGER;

-- Mengisi kolom bid_price dengan nilai harga mobil dalam ratusan juta dari tahun 2009 sampai 2022
UPDATE car_product SET bid_price = (200 + FLOOR(RANDOM() * (2023 - 200 + 1))) * 1000000
WHERE year BETWEEN 2009 AND 2022;

ISi Query yang ada di notepad satunya lagi ..
-- menambahkan satu data bid produk baru 
SELECT product_id, buyer_id, date_bid, bid_price, bid_status FROM car_product ORDER BY product_id ASC

-- contoh pernyataan SQL untuk menambahkan satu data bid produk baru
INSERT INTO car_product (product_id, brand, model, body_type, year, price, bid_price, bid_status, buyer_id, date_bid, date_post)
VALUES (51,'Toyota', 'Toyota Avanza', 'MPV', 2021, 230000000, 250000000, 'accepted', 123, '2023-10-30', '2023-10-30');

-- melihat mobil yang terjual dilihat dari akun terbaru
SELECT product_id, brand, model, year, price, date_post
FROM car_product
ORDER BY year DESC;



-- Menambahkan kolom bid_status dan buyer_id ke tabel car_product
ALTER TABLE car_product
ADD COLUMN bid_status VARCHAR(50),  -- Sesuaikan panjang karakter sesuai kebutuhan
ADD COLUMN buyer_id INTEGER;

-- Mengisi kolom bid_status dengan nilai random 'accepted' atau 'rejected'
UPDATE car_product SET bid_status = CASE WHEN RANDOM() > 0.5 THEN 'accepted' ELSE 'rejected' END;

-- Mengisi kolom buyer_id dengan nilai acak antara 1 dan 1000
UPDATE car_product SET buyer_id = FLOOR(RANDOM() * 1000) + 1;


-- Menambahkan kolom date_bid dan date_post ke tabel car_product
ALTER TABLE car_product
ADD COLUMN date_bid DATE,
ADD COLUMN date_post DATE;

-- Mengisi kolom date_bid dengan nilai random dari tahun 2020 sampai 2022
UPDATE car_product SET date_bid = DATE '2020-01-01' + INTERVAL '1 year' * (RANDOM() * 3)::INT;

-- Mengisi kolom date_post dengan nilai random dari tahun 2010 sampai 2022
UPDATE car_product SET date_post = DATE '2010-01-01' + INTERVAL '1 year' * (RANDOM() * 13)::INT;

-Maaf team pacmann dan mentor saya belum bisa membuat nya dengan rapi dan lengkap hanya ini yang saya bisa buat 🙏
