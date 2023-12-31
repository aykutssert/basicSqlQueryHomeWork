<img src="https://global-uploads.webflow.com/6097e0eca1e875de53031ff6/6241a5ec363584013b7b1857_Patika%20logo%20(2).png" alt="patika image" height="200px" width="200px">

# PATIKA HOMEWORKS

## Homework 1

<br><br>

1-) Film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.


```
SELECT title, description FROM film;

```
<br>

2-) Film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.


```
SELECT * FROM film
WHERE length > 60 AND length < 75;

```
<br>

3-) Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.


```
SELECT * FROM film
WHERE rental_rate = 0.99 AND (replacement_cost=12.99 OR  replacement_cost=28.99);

```
<br>

4-) customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

```
SELECT last_name FROM customer
WHERE first_name='Mary';

```
<br>

5-) film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

```
SELECT * FROM film
WHERE (NOT length>50) AND NOT( rental_rate = 2.99 OR rental_rate = 4.99)

```
<br><br>

## Homework 2

1-) film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
```
SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.99

```
<br>

2-) actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)
```
SELECT first_name , last_name FROM actor
WHERE first_name IN('Penelope','Nick','Ed')

```
<br>

3-) film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

```
SELECT *  FROM film
WHERE rental_rate IN(0.99, 2.99, 4.99) AND replacement_cost IN(12.99, 15.99, 28.99)

```
<br><br>

## Homework 3

1-) country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```
SELECT country FROM country
WHERE country LIKE 'A%a';
```
<br>

2-) country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```
SELECT country  FROM country
WHERE country LIKE '%_____n';
```
<br>
3-) film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```
SELECT title  FROM film
WHERE title ILIKE '%t%t%t%t%';
```
<br>

4-) film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.
```
SELECT *  FROM film
WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99;
```
<br><br>

## Homework 4

1-) film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

```
SELECT DISTINCT replacement_cost FROM film
```
<br>

2-) film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

```
SELECT COUNT(DISTINCT replacement_cost) FROM film
```

<br>

3-) film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```
SELECT COUNT(*) FROM film
WHERE title LIKE 'T%' AND rating='G';
```
<br>

4-) country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```
SELECT COUNT(DISTINCT country) FROM country
WHERE country LIKE '_____';
```
<br>

5-) city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?
```
SELECT COUNT(DISTINCT city) FROM city
WHERE city ILIKE '%R';
```
<br>
<br>

## Homework 5

1-) film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```
SELECT title , length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;
```

<br>

2-) film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.

```
SELECT title , length FROM film
WHERE title LIKE '%n'
ORDER BY length
OFFSET 5
LIMIT 5;
```

<br>

3-) customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

```
SELECT * FROM customer
WHERE store_id=1
ORDER BY last_name DESC
LIMIT 4;
```


