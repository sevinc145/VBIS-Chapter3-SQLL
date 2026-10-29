# Explanation

## 1. Ən çətin hesab etdiyiniz SQL sorğusu hansı oldu?

Mənə görə ən çox düşündürən sual 3.15(a) idi. Bu tapşırıqda Brooklyn-dakı bütün filiallarda hesabı olan müştəriləri tapmaq tələb olunurdu. Bunun üçün NOT EXISTS istifadə etdim. Yəni müştərinin hesabı olmayan hər hansı bir Brooklyn filialı olub-olmadığını yoxladım. Əgər belə filial yoxdursa, deməli, həmin müştərinin bütün Brooklyn filiallarında hesabı var.

## 2. Hansı sorğu üçün alt sorğu (subquery) istifadə etdiniz?

3.25-ci sualda alt sorğudan istifadə etdim. İlk olaraq daxili sorğu ilə Philosophy departamentinin büdcəsini tapdım. Daha sonra xarici sorğuda büdcəsi həmin məbləğdən çox olan departamentləri seçdim və nəticələri əlifba sırası ilə düzdüm. 3.11(d)-də isə FROM daxilində alt sorğu yazaraq hər departamentin maksimum maaşını müəyyən etdim, sonra MIN ilə bu göstəricilərin ən kiçiyini tapdım. 3.11(b)-də NOT IN, 3.15(c)-də isə SOME operatorundan istifadə edərək alt sorğularla işlədim.

## 3. JOIN istifadə etdiyiniz bir nümunəni izah edin.

3.24-cü tapşırıqda lazım olan məlumatları əldə etmək üçün JOIN vasitəsilə üç cədvəli əlaqələndirdim. student və advisor cədvəllərini tələbənin ID-si ilə, advisor və instructor cədvəllərini isə müəllimin ID-si ilə birləşdirdim. Daha sonra WHERE şərti ilə yalnız departamenti Accounting olan tələbələri və məsləhətçisinin departamenti Physics olan halları seçdim. Beləliklə, tələbələr və onların məsləhətçiləri haqqında lazım olan məlumatları əldə etdim.
## 4. SQL sorğularını yazarkən qarşılaşdığınız bir problemi və onun həllini izah edin.

3.11(a)-da `student`, `takes` və `course` cədvəllərindən istifadə etdim. Sorğunu yazanda bəzi tələbələrin adlarının bir neçə dəfə təkrarlandığını gördüm. Bu, həmin tələbələrin bir neçə Comp. Sci. kursunda iştirak etməsi ilə bağlı idi. Təkrarları aradan qaldırmaq üçün `SELECT` hissəsinə `DISTINCT` əlavə etdim və hər tələbənin adının yalnız bir dəfə göstərilməsini təmin etdim.

3.15(c)-də isə əvvəlcə `ALL` operatorundan istifadə etdiyim üçün nəticə düzgün alınmadı. Çünki `ALL` şərtin bütün filiallar üçün ödənilməsini tələb edirdi. Tapşırıqda isə ən azı bir filialla müqayisə aparmaq lazım idi. Buna görə `ALL` əvəzinə `SOME` yazdım və sorğunu tapşırığın şərtinə uyğunlaşdırdım.
