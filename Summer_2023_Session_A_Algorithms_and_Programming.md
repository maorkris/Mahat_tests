<div dir="rtl">


    חלק א׳       
#### ענו על ארבע מבין השאלות 6-1 (ערך כל שאלה – 12 נקודות) 

# 
שאלה 1
מספר שלם חיובי נקרא "מספר מושלם" אם הוא מתחלק בסכום ספרותיו.
לדוגמה:
מספר 12 הוא מספר מושלם, מספר 24 הוא מספר מושלם, מספר 25 אינו מספר מושלם. כתבו קטע תוכנית להדפסת כל המספרים המושלמים מ- 1 עד 1,000.



```python
def sum_of_num(num):
    # משתנה שמחזיק את סכום הספרות
    con = 0
    # עוברים על כל ספרה במספר
    for i in str(num):
        # מוסיפים את הספרה לסכום
        con += int(i)
    # מחזירים את סכום הספרות
    return con

def perfect_number():
    # משתנה שמחזיק את מספר המספרים המושלמים שמצאנו
    con = 0
    # עוברים על כל המספרים בטווח 1 עד 1000
    for i in range(1,1001):
        # בודקים אם המספר מתחלק בסכום הספרות שלו
        if i % sum_of_num(i) == 0:
            # אם כן, מגדילים את המונה של המספרים המושלמים ב-1
            con += 1
            # מדפיסים את המספר המושלם
            print(i, end=" ")

perfect_number()

#-------------------------------------------------#

def divides_dy_sum(num):
    sum_of_digits = 0                 #משתנה שסוכם את כל הספרןת של המספר שהתקבל  
    temp_num = num                    #משתנה זמני שמחזיק את המספר שהתקבל
    while temp_num > 0:               # לולאה שסוכמת את סיפרת האחדות של המשתנה הזמני שקיבל את הערך של המספר שהתקבל ואז חותכת אותו עד שהמספר שווה 0
        last_digit = temp_num % 10
        temp_num = temp_num // 10
        sum_of_digits += last_digit

    if num % sum_of_digits == 0:     # בדיקה בוליאנית אם המספר שקיבלנו מתחלק בסכום סיפרותיו בלי שארית
        return True
    return False


#  1000  פונקציה שניה מריצה לולאה עד 
# ובודקת על ידי הפונקציה למעלה האם המספר שהלולאה נמצאת מתחלק בסכום סיפרותיו 
# "True" אם התשובה היא 
# אז הפונקציה מדפיסה את המספר
#



def range_up():

    for i in range(1,1001):         # הרצת לולאה עד 1000 כדי לבדוק כל מספר אם הוא מתחלק בסכום סיפרותיו
        if divides_dy_sum(i):       # בדיקה על ידי הפונקציה למעלה האם המספר הזה מתחלק בסכום סיפרותיו
            print(i)                # הדפסת המספר שקיבלנו תשובה שהוא מתחלק בסכום סיפרותיו


range_up()                          # קריאה לפונקציה

# divides_dy_sum()


```



                                שאלה 2       
מחרוזת שמייצגת "מספר נייד תקין" היא מחרוזת העונה לשלושה תנאים: • שלושת התווים ראשונים הם קידומת (050, 051, 052, 053, 054, 055, 056, 057, 058). • התו הרביעי הוא מקף (-).
• שבעת התווים הבאים הם ספרות. לדוגמה: המחרוזת 050-1230567 היא מספר נייד תקין. כתבו קטע תוכנית הקולטת מחרוזות עד שתקלט מחרוזת שהיא מספר נייד תקין. יש להדפיס מספר המחרוזות שנקלטו.

```python
def valid_phone():
    # משתנה שמחזיק את מספר הניסיונות שלא הצליחו
    filed_chance = 0
    while True:
        # רשימת הקידומות התקניות
        prefix_number = '050', '051', '052', '053', '054', '055', '056', '057', '058'
        # בקשה מהמשתמש להזין מספר טלפון
        phone_number = input("Please Enter your Phone :")
        # הקידומת של המספר
        prefix = phone_number[:3]
        # הסימן שאמור להיות אחרי הקידומת
        score = '-'
        # שארית המספר לאחר הקידומת והסימן
        rest_of_phone_number = phone_number[4:]
        # בדיקה אם הקידומת נמצאת ברשימת הקידומות, הסימן הוא מקף ושארית המספר מורכבת מספרות בלבד
        if prefix in prefix_number and phone_number[3] == score and rest_of_phone_number.isnumeric():
            # אם המספר תקני, מחזירים את מספר הניסיונות שלא הצליחו ואת הערך True
            return f" After {filed_chance} \n the number is:{True}"
        else:
            # אם המספר לא תקני, מוסיפים 1 למשתנה שמחזיק את מספר הניסיונות שלא הצליחו
            filed_chance += 1


print(valid_phone())
```

                                שאלה 3  

 רשימה של מספרים שלמים נקרת "רשימה מסודרת" אם כל הערכים הזוגיים (אם יש כאלה) נמצאים בתחילת הרשימה וכל הערכים האי-זוגיים (אם יש כאלה) נמצאים אחריהם, בסוף הרשימה. לדוגמה: הרשימות הבאות הן רשימות "מסודרות":
                  lst1 = [6, 24, 12, 8, 44, 3, 7]
                  lst2 = [6, 24, 12, 8, 16, 22]
(6 נק') א. כתבו פעולה המקבלת רשימה של מספרים שלמים arr. הפעולה תחזיר ערך True, אם הרשימה "מסודרת" ולא, הפעולה תחזיר ערך False.
כותרת הפעולה:
is_ordered(arr)
(6 נק') ב. כתבו פעולה המקבלת שלושה פרמטרים מטיפוס מספר שלם: y ,x ,size.
הפעולה צריכה ליצור רשימה מסודרת של מספרים שלמים בגודל size המלאה במספרים אקראיים בין x ל- y (כולל). כותרת הפעולה:
                         build_ordered(size, x, y)
אפשר להניח ש- 0>size וגם x<y.

```python


def ordered_list(arr):
    # משתנה שמחזיק את האינדקס של המספר האי-זוגי הראשון ברשימה
    index = 0
    # עוברים על כל האינדקסים ברשימה
    for i in range(len(arr)):
        # בודקים אם המספר באינדקס הנוכחי הוא מספר אי-זוגי
        if arr[i] % 2 == 1:
            # אם כן, שמים את האינדקס שלו במשתנה index ומפסיקים את הלולאה
            index = i
            break
    else:
        # אם לא מצאנו מספר אי-זוגי, זה אומר שכל המספרים ברשימה הם זוגיים ולכן הרשימה מסודרת
        return True

    # עוברים על האינדקסים שלא בדקנו עדיין
    for j in range(index,len(arr)):
        # בודקים אם המספר באינדקס הנוכחי הוא מספר זוגי
        if arr[j] % 2 == 0:
            # אם כן, זה אומר שיש לנו מספר זוגי אחרי מספר אי-זוגי ולכן הרשימה לא מסודרת
            return False
    else:
        # אם לא מצאנו מספר זוגי אחרי מספר אי-זוגי, זה אומר שהרשימה מסודרת
        return True

# חלק ב'
import random

def oerdarr(x, y, size):
    # רשימה של מספרים זוגיים
    equal = []
    # רשימה של מספרים אי-זוגיים
    odd = []
    # עוברים על כל מספר מ-0 עד size
    for i in range(size):
        # מייצרים מספר אקראי בין x ל-y
        num = random.randint(x, y)
        # בודקים אם המספר הוא זוגי
        if num % 2 == 0:
            # אם כן, מוסיפים אותו לרשימת המספרים הזוגיים
            equal.append(num)
        else:
            # אם לא, מוסיפים אותו לרשימת המספרים האי-זוגיים
            odd.append(num)
    # מחזירים את הרשימה שמתחילה במספרים הזוגיים וממשיכה במספרים האי-זוגיים
    return equal + odd

print(ordered_list([6, 24, 12, 8, 44, 3, 7]))
print(oerdarr(1, 10, 10))

```

                                שאלה 4
 מייצגת נקודת זמן לפי מספר שעות ומספר דקות.המחלקה Time

```python
class Time:
    def __init__(self, hour, minutes):
        self.hour = hour
        self.minutes = minutes
```

א. כתבו במחלקה  פעולה המקבלת הפניה לאובייקט מטיפוס  ״זמן״ ומחזירה את מספר הדקות שעברו בין הזמן המיוצג על-ידי האובייקט שמפעיל את הפעולה (self ) לזמן המיוצג באמצעות  other. 

אפשר להניח ש- self לפני other.

 ב. חברת משלוחים מבטיחה ללקוחותיה שכל משלוח יגיע למען לא מאוחר משלוש שעות (180 דקות) מהרגע שהתקבל בחברה. 

כתבו קטע תוכנית לבדיקה. הקטע צריך לקלוט עבור כל אחד מ- 100 משלוחים את זמני קבלתו בחברה ומסירתו לידי הלקוח. עבור כל משלוח ייקלטו ארבעה מספרים שלמים. לדוגמה: עבור משלוח שהתקבל בחברה ב- 10:50 ונמסר ללקוח ב- 12:20 יש לקלוט ארבעה מספרים: 10, 50, 12, 20. קטע התוכנית יבדוק אם חברת המשלוחים קיימה את ההבטחה וידפיס הודעה מתאימה. עליכם להיעזר בפעולה שכתבתם בסעיף א'. 


```python

class Time:
    # פונקציית האתחול של המחלקה, מקבלת שעה ודקות ומאתחלת את האובייקט
    def __init__(self, hour, minutes):
        self.hour = hour
        self.minutes = minutes

    # פונקציה שמחשבת את ההפרש בין שני זמנים
    def difference(self,other):
        # מחשבים את הזמן של האובייקט השני בדקות
        other_time = (other.hour * 60) + other.minutes
        # מחשבים את הזמן של האובייקט הנוכחי בדקות
        self_time = (self.hour * 60) + self.minutes
        # מחזירים את ההפרש בין הזמנים בדקות
        return abs(other_time - self_time)


# לולאה שרצה פעם אחת (במקור השאלה הרצה- 100 פעמים)

for i in range(1):
    # מבקשים מהמשתמש להזין שעה ודקות לזמן הראשון
    self_hour = int(input("לזמן הראשון -> אנא הזן שעה (בפורמט 24 שעות):"))
    self_min = int(input("לזמן הראשון -> אנא הזן דקות:"))
    # מבקשים מהמשתמש להזין שעה ודקות לזמן השני
    outer_hour = int(input("לזמן השני -> אנא הזן שעה (בפורמט 24 שעות):"))
    other_min = int(input("לזמן השני -> אנא הזן דקות:"))

    # יוצרים שני אובייקטים של זמן
    first = Time(self_hour,self_min)
    second = Time(outer_hour,other_min)

    # בודקים אם ההפרש בין הזמנים גדול מ-180 דקות
    if Time.difference(first, second) > 180:
        print(f"ההפרש הוא {Time.difference(first, second)} דקות. \nההפרש גדול מ-180 דקות, זהו משלוח לא חוקי.")
    else:
        print(f"ההפרש הוא {Time.difference(first, second)} דקות. \nזהו משלוח חוקי.")
```


                                שאלה 5

נתונה הפעולה what המקבלת רשימה של מספרים שלמים באורך זוגי
```python
def what(a):
    length = len(a)
    for i in range(2,length-1,2):
        if a[i]<a[i-2]:
            return False
        i+=1
        if a[i]>a[i-2]:
            return False
    return True
```


נתונה רשימה מספרים שלמים a:

  ` a = [1, 25, 3, 8, 10, 4, 20, 5]`


(5 נק') א. עקבו בעזרת טבלת מעקב אחרי ביצוע הפעולה ורשמו מה תחזיר הפעולה.


טבלת מעקב היא כלי שמשמש לבדיקת תקינות וניפוי שגיאות בקוד. היא מאפשרת לעקוב אחר הערכים של המשתנים והביטויים בכל שלב של הרצת הקוד, ולוודא שהם תואמים את הציפיות.
<img width="844" alt="צילום מסך 2024-01-30 ב-21 58 11" src="https://github.com/maorkris/Mahat_tests/assets/142143890/d31587f7-e713-4f68-b116-3eb0b8d140a7">


לאחר מעקב : הפעולה החזירה את הערך False 


(2 נק') ב. תנו דוגמה לרשימה בגודל עשרה ערכים שעבורו הפעולה `what` תחזיר ערך `True`.

`a = [1, 10, 3, 8, 5, 6 , 7, 2, 9,0]`
הרשימה הזו תחזיר ערך `True`


(2 נק') ג. מה מבצעת הפעולה what באופן כללי?


`הפעולה what  בודקת האם אברי המערך a  אותו היא מקבלת , עולים עבור האינדקסים הזוגיים ויורדים באינדקסים האי זוגיים.`


(3 נק') ד. נתונה רשימה b של מספרים שלמים. ידוע שתוצאת הזימון what(b) היא True.


כתבו פעולה יעילה ככל האפשר, המחזירה את הערך הגדול ביותר ברשימה b. מהי סיבוכיות הפעולה שכתבתם?

```python
def big_value(b):
    
    if b[1] > b[len(b)-2]:
        print(b[1])
    else:
        print(b[len(b) -2])

```

סיבוכיות הפעולה היא O(1) כיוון שהפעולה מבצעת פעולות קבועות ולא תלויות באורך הרשימה.

### חלק ב' ###
#### ענו על שתיים מבין השאלות 9-7 (ערך כל שאלה – 15 נקודות).


<<<<<<< HEAD
                                שאלה 7 

נתונה המחלקה Coffee, המייצגת קפסולות למכונת קפה. תכונות המחלקה הן:
• שם היצרן – name, מטיפוס מחרוזת – string. • סוג קפה – kind, מטיפוס מחרוזת – string. • רמת החוזק – strength, מטיפוס מספר שלם – int (בין 1 ל-12).
• מחיר – price, מטיפוס מספר ממשי – float. במחלקה הוגדרה פעולה בונה (constructor) המקבלת פרמטר לכל תכונה ויוצרת עצם סוג Coffee, המכיל את הערכים האלו בתכונות.


(5 נק') א. כתבו פעולה המקבלת רשימה של עצמים מסוג Coffee. הפעולה תבדוק שכל הקפסולות הן מאותו יצרן. אם כן – הפעולה תחזיר ערך True, ולא – תחזיר False.
כותרת הפעולה:
same_products(crr)

(5 נק') ב. כתבו פעולה המקבלת רשימה של עצמים מסוג Coffee ומספר שלם חיובי num.
הפעולה תחזיר רשימה חדשה הכוללת את סוגי קפה שרמת החוזק שלהם קטנה מ- num. אם אין רשימה אף קפסולה שרמת החוזק שלה קטנה מ- num, הפעולה תחזיר רשימה ריקה. כותרת הפעולה:
weak_sorts(crr, num)

(5 נק') ג. כתבו פעולה המקבלת רשימה של עצמים מסוג Coffee. הפעולה תדפיס את פרטי הקפסולות  **היקרות ביותר.**
כותרת הפעולה:

most_expensive(crr)


```python
class Coffee:
    def __init__(self, name, kind, strength, price):
        self.name = name  # שם הקפה
        self.kind = kind  # סוג הקפה
        self.strength = strength  # חוזק הקפה
        self.price = price  # מחיר הקפה

    def same_products(crr):
        # פונקציה שבודקת אם כל המוצרים ברשימה זהים
        for i in range(len(crr)-1):  # עובר על כל הרשימה
            if crr[i].name != crr[i+1].name:  # בודק אם שני מוצרים רצופים לא זהים
                return False  # אם לא זהים, מחזיר False
        return True  # אם כל המוצרים זהים, מחזיר True

    def weak_sorts(crr, num):
        # פונקציה שמחזירה רשימה של סוגי המוצרים שחוזקם פחות מהמספר שהוזן
        arr = []  # יוצר רשימה ריקה
        for i in crr:  # עובר על כל הרשימה
            if i.strength < num:  # בודק אם החוזק של המוצר פחות מהמספר שהוזן
                arr.append(i.kind)  # אם כן, מוסיף את הסוג של המוצר לרשימה
        return arr  # מחזיר את הרשימה

    def most_expensive(crr):
        # פונקציה שמחזירה את המוצר היקר ביותר
        biggest = 0  # משתנה שמחזיק את המחיר הגבוה ביותר
        for i in crr:  # עובר על כל הרשימה
            if i.price > biggest:  # בודק אם המחיר של המוצר גבוה יותר מהמחיר הגבוה ביותר שנמצא עד כה
                biggest = i.price  # אם כן, מעדכן את המחיר הגבוה ביותר

        for kind in crr:  # עובר על כל הרשימה שוב
            if kind.price == biggest:  # בודק אם המחיר של המוצר שווה למחיר הגבוה ביותר
                print(kind.name,kind.kind,kind.strength,kind.price)  # אם כן, מדפיס את המוצר



c1 = Coffee("x", "black", 10, 10)  # יוצר מוצר חדש של קפה שחור
c2 = Coffee("x", "Vanil", 5, 10)  # יוצר מוצר חדש של קפה וניל
c3 = Coffee("x", "Ness", 2, 10)  # יוצר מוצר חדש של קפה נס

crr: list[Coffee] = [c1, c2, c3]  # יוצר רשימה של מוצרים

```
=======
>>>>>>> origin/master

                                שאלה 8 
(5 נק') א׳

כתבו פעולה המקבלת שתי רשימות של מספרים שלמים ובודקת אם הן הפוכות. אם כן – הפעולה תחזיר ערך `True`, ולא – תחזיר ערך `False`.




```python
def revers(lst1,lst2):
    """
    פונקציה שמקבלת שתי רשימות של מספרים שלמים ובודקת אם הן הפוכות.
    אם הן הפוכות, הפונקציה מחזירה True, אחרת היא מחזירה False.

    :param lst1: רשימה של מספרים שלמים
    :param lst2: רשימה של מספרים שלמים
    :return: True אם הרשימות הן הפוכות, False אחרת
    """
    # עוברים על כל האינדקסים ברשימה הראשונה
    for i in range(len(lst1)):
        # בודקים אם האיבר באינדקס הנוכחי ברשימה הראשונה שונה מהאיבר באינדקס המתאים ברשימה השנייה
        # האינדקס המתאים ברשימה השנייה הוא האינדקס ההפוך (-1-i)
        if lst1[i] != lst2[-1-i]:
            # אם מצאנו איבר ששונה, מחזירים False ומפסיקים את הלולאה
            return False
    # אם לא מצאנו איבר ששונה, מחזירים True
    return True
```

לדוגמא :
```python
a = [1, 25, 3, 8, 10, 4, 20, 5]
b = [5, 20, 4, 10, 8, 3, 25, 1]

print(revers(a, b))  # יחזיר True
```


(1 נק') ב.
מהי הסיבוכיות של הפעולה שכתבתם? הסבירו את תשובתכם:

`הסיבוכיות של הפעולה היא O(n), כאשר n הוא אורך הרשימה. הסיבה לכך היא שאנו עוברים על כל איבר ברשימה בדיוק פעם אחת. במהלך כל איטרציה, אנו בודקים אם האיבר ברשימה הראשונה שונה מהאיבר המתאים ברשימה השנייה, פעולה שמתבצעת בזמן קבוע. לכן, הסיבוכיות הכוללת של הפעולה היא פרופורציונלית לאורך הרשימה, כלומר O(n).`


                                שאלה 9



נתונה מחלקה Digits המתארת ספרות של מספר שלם וחיובי. למחלקה Digits תכונה אחת בלבד arr_digits – רשימה בת עשרה ערכים מטיפוס מספר שלם, המייצגת את מספר הפעמים שבו כל ספרה בין 0‐9 מופיעה במספר.
<img width="879" alt="צילום מסך 2024-01-29 ב-23 01 30" src="https://github.com/maorkris/Mahat_tests/assets/142143890/6f5d0ee7-f67c-4e06-b00b-c6ec1af02320">



(4 נק') א. כתבו במחלקה Digits פעולה בונה (constructor) המקבלת כפרמטר מספר שלם חיובי
כלשהו ומאתחלת את התכונה arr_digits בהתאם (כלומר הרשימה תכיל את מספר הפעמים שכל ספרה מופיעה בו).
```python
class Digits:
    def __init__(self,num):
        """
        פונקציית האתחול של המחלקה. מקבלת מספר ומאתחלת את האובייקט עם רשימה של ספרות המספר.
        :param num: המספר שעליו נבנה האובייקט
        """
        # מאתחל רשימה של 9 אפסים
        arr_digits = [0,0,0,0,0,0,0,0,0]
        # עובר על כל ספרה במספר
        for i in str(num):
            # מוסיף 1 למקום המתאים ברשימה
            arr_digits[int(i)] += 1

        # שומר את הרשימה במשתנה של האובייקט
        self.num = arr_digits
```
**לדוגמא עבור הקריאה הבאה לפונקציה:**
```python
print(Digits(123).num)
```
**יתקבל הפלט:**
```python
[0, 1, 1, 1, 0, 0, 0, 0, 0, 0]
```
מכוון שבמספר 123 יש ספרה 1 אחת, ספרה 2 אחת וספרה 3 אחת.

________________________________________

(3 נק') ב. כתבו במחלקה Digits פעולה equals המקבלת הפניה לעצם אחר מטיפוס Digit.
הפעולה תחזיר ערך True אם שני העצמים זהים, ולא – הפעולה תחזיר ערך False.

```python

    def equals(self,other_Digit):
        """
        פונקציה שמקבלת הפניה לאובייקט אחר מטיפוס Digits ובודקת אם שני האובייקטים זהים.
        אם הם זהים, הפונקציה מחזירה True, אחרת היא מחזירה False.
        :param other_Digit: האובייקט השני שנבדוק את האובייקט הנוכחי איתו
        :return: True אם האובייקטים זהים, False אחרת
        """
        return self.num == other_Digit.num
```
(3 נק') ג. נתון קטע הבא:
```python
num1 = int(input("first number:"))
num2 = int(input("second number:"))
dg1=Digits(num1)
dg2=Digits(num2)
if dg1.equals(dg2):
    print("the numbers are equal")
else:
    print("the number are not equal")
```
האם הפעולה מדפיסה תוצאה נכונה עבור כל זוג מספרים שלמים וחיובים num1 ו-num2? הסבירו את תשובתכם.

`במידה והשאלה מתייחסת למספר עצמו התשובה היא שלילית, מכיוון שייתכנו זוג מספרים שאינם שווים בספרותיהם כגון : 123 ו 312 שאינם שווים בערכם ועדין הפונקציה תחזיר ״המספרים שווים״ וזאת מכוון שהפונקציה quals   בודקת אם הarr digit  שלהם שווה ולא המספר עצמו. `
________________________________________
(5 נק') ד. כתבו במחלקה Digits פעולה compare_to המקבלת כפרמטר הפניה לעצם other מטיפוס Digits.
- הפעולה תחזיר 1 אם מספר המיוצג על ידי העצם המפעיל את הפעולה (this) גדול ממספר המיוצג על ידי העצם שהתקבל כפרמטר (other).
- הפעולה תחזיר 2 אם המספר המיוצג על ידי העצם המפעיל את הפעולה (this) קטן מהמספר המיוצג על ידי העצם שהתקבל כפרמטר (other).
- אם אין אפשרות לתשובה חד משמעית, הפעולה תחזיר 0.


```python
def compare_to(self,other_Digit):
    """
    משווה בין שני אובייקטים.
    :param other_Digit: האובייקט להשוואה
    :return: 0 אם האובייקטים שווים, 1 אם האובייקט הנוכחי גדול, 2 אם האובייקט האחר גדול
    """
    # מאתחל משתנים לסכום, מונה ואינדקס של האובייקט הנוכחי והאחר
    sum_self = 0
    sum_other = 0
    counter_self = 0
    counter_other = 0
    index_self = None
    index_other = None

    # עובר על כל האיברים ברשימה של האובייקט הנוכחי
    for s in range(len(self.num)):
        # אם האיבר לא שווה לאפס, מוסיף 1 למונה ושומר את האינדקס
        if self.num[s] > 0:
            counter_self += 1
            index_self = s
        # מוסיף את האיבר לסכום
        sum_self += self.num[s]

    # עובר על כל האיברים ברשימה של האובייקט האחר
    for o in range(len(other_Digit.num)):
        # אם האיבר לא שווה לאפס, מוסיף 1 למונה ושומר את האינדקס
        if other_Digit.num[o] > 0:
            counter_other += 1
            index_other = o
        # מוסיף את האיבר לסכום
        sum_other += other_Digit.num[o]

    # אם הסכומים שווים
    if sum_self == sum_other:
        # אם המונים שווים
        if counter_other == counter_self:
            # אם האינדקסים שווים
            if index_self == index_other:
                return 0
            # אם האינדקס של האובייקט הנוכחי גדול יותר
            elif index_self > index_other:
                return 1
            # אם האינדקס של האובייקט האחר גדול יותר
            elif index_other > index_self:
                return 2

        # אם אחד המונים גדול מ-1
        if counter_other or counter_self > 1:
            return 0
        # אם האינדקס של האובייקט הנוכחי גדול יותר
        elif index_self > index_other:
            return 1
        # אם האינדקס של האובייקט האחר גדול יותר
        else:
            return 2

    # אם הסכום של האובייקט הנוכחי גדול יותר
    elif sum_self > sum_other:
        return 1

    # אם הסכום של האובייקט האחר גדול יותר
    else:
        return 2
```




                                שאלה 10


```python

class Room:
    def __init__(self, kind, area, freq):
        self.kind = kind  # סוג החדר
        self.area = area  # שטח החדר
        self.freq = freq  # תדירות הניקיון


class App:
    def __init__(self, app_num, owner, rooms, rate):
        self.app_num = app_num  # מספר הדירה
        self.owner = owner  # בעל הדירה
        self.rooms = rooms  # רשימת החדרים
        self.rate = rate  # מחיר למטר מרובע



class Building:
    def __init__(self, address, apartments):
        self.address = address  # כתובת הבניין
        self.apartments = apartments  # רשימת הדירות

    def month_report(self, builds, clients):
        for client_name in clients:
            for build in builds:
                for app in build.apartments:
                    if client_name == app.owner:
                        total_cost = 0
                        print(f"Owner: {app.owner}\nApartment Number: {app.app_num}")
                        for room in app.rooms:
                            print(f"Room Type: {room.kind}, Area: {room.area}, Cleaning Frequency: {room.freq}")
                        cost = app.month_cost()
                        print(f"Monthly Cleaning Cost for the Apartment: {cost}")
                        total_cost += cost
                        print(f"Total Cost for {app.owner}: {total_cost}\n")

# יצירת חדרים
room1 = Room("bedroom", 15, 1)
room2 = Room("living room", 20, 2)
room3 = Room("kitchen", 10, 1)

# יצירת דירות
app1_rooms = [room1, room2, room3]
app1 = App(1, "avi", app1_rooms, 10)

app2_rooms = [room1, room2]
app2 = App(2, "dani", app2_rooms, 12)

app3_rooms = [room3]
app3 = App(3, "moshe", app3_rooms, 8)

# יצירת בניינים
building1 = Building("Tel Aviv", [app1, app2])
building2 = Building("Jerusalem", [app3])
builds = [building1, building2]


```

מימוש שאלה ב׳ 

```python
# חישוב העלות החודשית לניקיון כל דירה
print(f"Monthly cleaning cost for apartment 1: {app1.month_cost()}")
print(f"Monthly cleaning cost for apartment 2: {app2.month_cost()}")
print(f"Monthly cleaning cost for apartment 3: {app3.month_cost()}")
```

מימוש שאלה ג׳

```python
# קריאה לפעולה המדפיסה דוח חודשי
building1.month_report(builds, ["avi", "dani", "moshe"])
```



                                שאלה 11
בחנות קיים מבנה נתונים מסוג מילון המייצג רשימת מוצרים ומחירם בהתאם ליחידת מוצר.
     prices = {'apple':10.0, 'banana': 6.5, 'milk':6.90т, ....}


(6 נק') א. דני מגיע לחנות עם רשימת קניות שאימא שלו הכינה:
shopping_list=[('apple',3),('milk',2),('coca-cola', 3)...] כתבו פעולה המקבלת מילון מוצרים prices ורשימת קניות shopping_list. הפעולה תחשב ותחזיר סכום כולל שדני חייב לשלם.


(5 נק') ב. מירי, אחותו הקטנה של דני, מתכוננת למסיבת היום הולדת שלה, וביקשה מדני לבדוק האם כל מה שהיא רוצה אפשר לקנות בחנות. לשם כך היא הכינה רשימת מוצרים שלה:
sister_list = ['milky', 'shoko', 'fries'..]


כתבו פעולה המקבלת מילון מוצרים prices ורשימה sister_list. הפעולה תיצור ותחזיר
def what1(num):
    if num == 0:
        return 1
רשימה מוצרים מתוך רשימה של מירי שחסרים בחנות.

```python
def Shopping(price:dict, shopping_list:list, sister_list:list):
    # משתנה שמחזיק את הסכום של המוצרים
    con = 0
    # עובר על כל המוצרים והכמות שלהם ברשימת הקניות
    for product,Quantity in shopping_list:
        # בודק אם המוצר נמצא במחירון
        if product in price:
            # מוסיף לסכום את מחיר המוצר כפול הכמות שלו
            con += Quantity * price[product]

    # מדפיס את הסכום של המוצרים
    print(f"{con}")

    # רשימה שמחזיקה את המוצרים שאינם נמצאים במחירון
    Missing_products = []

    # עובר על כל המוצרים ברשימת האחות
    for item in sister_list:
        # בודק אם המוצר אינו נמצא במחירון
        if item not in price:
            # מוסיף את המוצר לרשימת המוצרים שאינם נמצאים במחירון
            Missing_products.append(item)

    # מדפיס את המוצרים שאינם נמצאים במחירון
    print(f"item the are missing : {Missing_products}")


# רשימת המוצרים של האחות
sister_list = ['milky', 'shoko', 'fries', "milk"]
# מחירון המוצרים
price = {"Apple": 10.0, "Banana": 6.5, "milk": 6.90}
# רשימת הקניות
shopping_list = [("milk", 2), ("Apple", 3), ("Coca cola", 3)]
# מדפיס את התוצאה של הפונקציה Shopping
print(Shopping(price, shopping_list, sister_list))
```


</div>
