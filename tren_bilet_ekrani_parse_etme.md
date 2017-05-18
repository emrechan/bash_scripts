# Tren Bilet Ekrani Parse Etme

1. Sayfanin source code'u bir dosyaya kayit edilir (<input_filename>).
2. Asagidaki komut calistirilir.
```bash
grep -i "<center" <input_filename> | grep -v button | grep -v input | sed -e 's/\t//g' | awk '{ printf $1 }' | sed -e 's/<center>Geçerli/\n/g' | grep -v table | sed -e 's/<center>/\t/g' | sort -k2,2 -k1,1 > <output_filename>
```
3. Cikti <output_filename> dosyasindan okunur.
