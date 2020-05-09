# Credit Card Number Validator

## Краткое описание

9.04.2020 было проведено тестирование Credit Card Number Validator

На тестирование затрачено: 1 час

В результате тестирования выявлены следующие дефекты:

* <>
* <>
* <>
* <>

## Описание процесса тестирования

В процессе тестирования использовались следующие артефакты:

* Инструкция по установке  IntelliJ IDEA: <https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md>
* пример формы отчётности: <https://github.com/netology-code/javaqa-homeworks/blob/master/intro/report.md>
* программный код из задания:
``` public class Main {
      public static void main(String[] args) {
        // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
        String number = "5351719427810741";
        System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
      }
    
      public static boolean isValidCardNumber(String number) {
        if (number == null) {
          return false;
        }
    
        if (number.length() != 16) {
          return false;
        }
    
        long result = 0;
        for (int i = 0; i < number.length(); i++) {
          int digit;
          try {
            digit = Integer.parseInt(number.charAt(i) + "");
          } catch (NumberFormatException e) {
            return false;
          }
    
          if (i % 2 == 0) {
            digit *= 2;
            if (digit > 9) {
              digit -= 9;
            }
          }
          result += digit;
        }
    
        return (result != 0) && (result % 10 == 0);
      }
    }
``` 

В качестве тестовых данных использовались данные с сайта:
 * <https://www.freeformatter.com/credit-card-number-generator-validator.html>
 * ExampleCards.md <>

Тестирование производилось в следующем окружении:

* Windows 10 x64
* IntelliJ IDEA 2020.1.1 (Community Edition)
