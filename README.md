# OTO 101 Veritabanı Dokümantasyonu

## 1.Giriş
Bu veritabanı, OTO101 adlı oto yedek parça satan bir e-ticaret websitesinin ürünlerini yönetmek için kullanılır. Bu dokümantasyon, veritabanının yapısını ve kullanımını açıklar 

## 2.Veritabanı Tanıtımı 

- **Veritabanı Adı:** Oto101 Products
- **Tür:** İlişkisel
- **Platform:** MySQL 13.0
- **Version:** 1.0

## 3.Veri Modeli

- **products table:**
    - 'id' (integer)
    - 'name' (string)
    - 'brand_id' (integer)
    - 'code' (string)
    - 'slug' (string)
    - 'description' (text)
    - 'image' (string)
    - 'tax_ratio' (decimal)
    - 'category_id' (integer)
    - 'length' (decimal)
    - 'width' (decimal)
    - 'height' (decimal)
    - 'weight' (decimal)
    - 'desi' (decimal)
    - 'take_away' (boolean)
    - 'size' (decimal)
    - 'barcode' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **product_images table:**
    - 'id' (integer)
    - 'product_id' (integer)
    - 'image' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **oems table:**
    - 'id' (integer)
    - 'oem' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **product_oems table**
    - 'id' (integer)
    - 'product_id' (integer)
    - 'oem_id' (integer)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **suppliers table**
    - 'id' (integer)
    - 'name' (string)
    - 'first_name' (string)
    - 'last_name' (string)
    - 'phone' (integer)
    - 'email' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **product_suppliers table**
    - 'id' (integer)
    - 'name' (string)
    - 'stock' (integer)
    - 'price' (decimal)
    - 'product_id' (integer)
    - 'supplier_id' (integer)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **market_places table**
    - 'id' (integer)
    - 'name' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string) 
    - 'updated_by' (string)

- **market_places_categories table**
    - 'id' (integer)
    - 'category_id' (integer)
    - 'market_place_id (integer)
    - 'market_place_category_id (integer)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **market_places_products table**
    - 'id' (integer)
    - 'market_place_id' (integer)
    - 'price' (decimal)
    - 'stock' (integer)
    - 'is_active' (boolean)
    - 'product_id' (integer)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **categories table**
    - 'id' (integer)
    - 'name' (string)
    - 'parent_id' (integer)
    - 'slug' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **brands table**
    - 'id' (integer)
    - 'name' (string)
    - 'slug' (string)
    - 'description' (text)
    - 'logo' (string)
    - 'keywords' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)
      
- **cars table**
    - 'id' (integer)
    - 'name' (string)
    - 'logo' (string)
    - 'slug' (string)
    - 'description' (text)
    - 'keywords' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **years table**
    - 'id' (integer)
    - 'name' (string)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **car_models table**
    - 'id' (integer)
    - 'name' (string)
    - 'car_id' (integer)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **car_model_years table**
    - 'id' (integer)
    - 'car_model_id' (integer)
    - 'year_id' (integer)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)

- **product_model_years table**
    - 'id' (integer)
    - 'product_id' (integer)
    - 'model_years_id' (integer)
    - 'created_at' (string)
    - 'updated_at' (string)
    - 'created_by' (string)
    - 'updated_by' (string)


## 4.Veri Yapısı

- Oto101 DB, PostgreSQL veritabanı kullanılarak barındırılmaktadır.
  
- Product table, ürünlerin bilgilerini depolamak için kullanılır.
  
- Ürünlerin kategorilerle ve markalarla ilişkisi ID ile sağlanır.

- Index'ler, sorgu performansını artırmak için kullanılır.

## 5.Güvenlik ve Erişim Kontrolleri

- Veritabanı erişimi sadece yetkilendirilmiş kullanıcılar tarafından yapılabilir.

- Farklı kullanıcı rolleri tanımlanmıştır.

## 6.Veritabanı Bakımı

- Veritabanı düzenli olarak izlenir ve sorunların tespiti için analiz edilir.

- Haftalık tam yedekleme ve günlük/incremental yedekleme süreçleri vardır.

- Veritabanı performansı düzenli olarak izlenir ve gerektiğinde optimize edilir.

## 7.Referanslar ve Ek Bilgiler

- PostgreSQL Resmi Belgeleri: [PostgreSQL] (https://www.postgresql.org/docs/)

- Şirket içi veritabanı yöneticisi ve geliştiricilerle iletişim kurun.
  
   

 


  
