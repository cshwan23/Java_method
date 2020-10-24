# Java_method
메소드



[메소드]

지금까지 배운 것으로도 얼마든지 프로그램으 만들 수 있다. 반복문, 조건문, 변수, 상수와 같은 것들은 사실상 프로그램을 만드는 가장 중요한 도구들이라고 할 수 있다. 지금부터 배우게 될 메소드나 객체지향과 같은 개념들은 웅장하고, 결함이 없고, 유지보수가 쉬운 애플리케이션을 만들기 위한 기법들이라고 할 수 있다. 이것들 없이도 프로그램을 만들 수는 있지만, 이것들 없이 규모있는 애플리케이션을 만든다는 것은 현실적으로 어려운 일이다. 지금까지 만드는 방법을 배웠다면 이제부터는 잘 만드는 방법을 익히는 것이라고 해도 과언이 아니다. 


[메소드]

메소드(method)는 코드를 *재사용할 수 있게 해준다. 이번 시간에는 경제적으로 로직을 작성하는 방법에 대해서 알아볼 것이다.

[메소드의 형식]

여러분은 이미 메소드를 만들고 사용했다. 아래 문장을 살펴보자.

      public static void main(String[] args){
        return
      }
      
이것이 메소드다. 지금깢 수없이 만들었던 저 main이라고 하는 것이 바로 메소드인 것이다. 위의 그림을 자세히 보면 void main(String[] args) { return } 부분과 public static 부분이 있다. 이 중에서 public static 부분은 이번 토픽에서 다루지 않을 개념이다. 이것들은 객체지향과 함께 언급되어야 본질을 이해할 수 있기 때문에 여기서는 언급하지 않겠다. 메소드를 만들 때 public static이라고 적어야 한다고 일단은 기계적으로 이해하자. 여러분이 주목할 것은 void main(String[] args){ return } 부분이다.


[메소드의 정의와 호출]

직접 메소드를 만드는 것을 정의라고 하고,
만들어진 메소드를 실행하는 것을 호출이라고 한다. 
아래의 예제를 보자.


      package org.opentutorials.javatutorials.method;
      
      public class MethodDemo1 {
      
      
          public static void numbering() {
          
              int i = 0;
              
              while ( i < 10 ) {
              
                  System.out.println(i);
                  
                  i++;
                  
               }
           }
           
          public static void main(String[] args) {
          
             numbering();
      
      
          }
      
      }

  public static void numbering() {
    int i = 0;
     while ( i < 10 ) {
     System.out.println(i);
     i++;
    }
    }   
    이 부분은 위의 numbering 이라는 이름의 메서드를 정의하고있다.
    이 메소드는 main이라는 이름의 메소드 안에서 호출되고 있다. 
    
          int i = 0;
              
              while ( i < 10 ) {
              
                  System.out.println(i);
                  
                  i++;
   이부분의 코드를 numbering이라는 이름의 메소드로 묶어서 외부로 분리한 것이다. 
   그리고 메소드 numbering의 로직이 필요할 때 numbering();이라고 하면 메소드 numbering의 로직이 실행된다.
   
   [main]
   
   자그럼 main 메소드가 무엇인지 알아보자. main 메소드는 규칙이다. 
   내가 만들고 싶은 프로그램이 있다면 반드시 public static void main(String[] args)가 이끄는 중괄호 안에 실행되기를 기대하
   는 로직을 위치시켜야 한다. 이것은 약속이기 때문에 나는 이 약속을 지켜야 한다. 그렇게 코드르 작성하면 자바를 실행하 때 자바는 내가
   작성한 main 메소드를 실행하게 되는 것이다. 
   나는 main 메소드를 작성하고, 자바는 main 메소드를 실행하는 관계라고 할 수 있다.
   
      
  [메소드가 없다면?]

아래 예제를 보자 반복문 수업에서 0부터 9까지 출력하는 애플리케이션을 만들었다. 그런데 0부터 9까지를 5번 출력해야 한다면 어떻게 해야 할까? 아래와 같이 해야할 것이다.


    public static void main(String[] args) {
    
        int i = 0;
        
        while (i<10) {
            System.out.println(i);      
            i++;        
         }
         int i = 0;
        
        while (i<10) {
            System.out.println(i);      
            i++;        
         }
        int i = 0;
        
        while (i<10) {
            System.out.println(i);      
            i++;        
         }
          int i = 0;
        
        while (i<10) {
            System.out.println(i);      
            i++;        
         }
         int i = 0;
        
        while (i<10) {
            System.out.println(i);      
            i++;        
         }
      }  
    }
    
  이정도는 복붙 해볼만 하다. 하지만 만약 이것을 1000번 해야 한다면? 각각으 로직이 1000줄에 육박한다면?
  그리고 그 내용을 수정해야한다면? 
  메소드르 사용한다면 결과는 같지만 로직은 단 한번만 등장한다. 이러한 것을 재활용성이라 한다.
  
    public static void numbering() {
      int i = 0;
      while (i<10) {
        System.out.println(i);
        i++;
      }
    }
    
    public static void main(String[] args){
      numbering();
      numbering();
      numbering();
      numbering();
      numbering();
    }
    
 [입력과 출력]
 
지금까지 메소드의 첫 번째 면모이 재활용성에 대해서 알아봤다. 자주 사용하는 로직을 메소드로 만들어두면 호출하는 것을 통해서
간편하게 로직을 재활용할 수 있다. 이제 메소드의 두번째 면모를 살펴볼 것인데 입력과 출력이다.
 
살아있는 것들은 외부의 자극에 따라서 반응한다. 외부의 자극이 입력이라면 반응은 출력이라고 할 수 있다. 우리가 아는 쓸모있는 대부분으 프로그램이 사용자의 입력에 따라 다른 결과를 출력한다.

메소드는 프로그램 안에서 동작하는 하나의 작은 프로그램이라고 할 수 있다. 위에서 살펴본 numbering이라는 메소드는 항상 똑같은 동작만을 반복한다. 이것도 재활용이라는 측면에서는 장점이지만, 입력 값에 따라서 출력 값을 달리 제공한다면 더욱 쓸모 있는 프로그램이 될 수 있을 것이다.

[매개변수와 인자]

메소드의 입력 값은 매개변수(parameter)를 통해서 이루어진다. 위의 예제를 조금 개선해보자.
이전 예제는 0부터 9까지의 숫자를 화면에 출력했다. 만약 필요에 따라 0부터 4까지 출력하고 싶거나 0부터 8까지 출력하고 싶다면 어떻게 해야 할까? 각각에 맞는 메소드를 새로 정의해야 할까? 그렇게 해도 되지만 더 좋은 방법이 있다. 입력 값에 따라서 다른 출력 값을 갖도록 메소드를 정의하면 된다. 즉 입력을 고민할 때가 된 것이다. 아래의 예제를 보자.



      public class MethodDemo4 {
      
        public static void numbering(int limit) {
        
            int i = 0;
            while (i < limit) {
            
                System.out.println(i);
                
                i++;
                }
              }
              
          public static void main(String[] args) {
          
            numbering(5);
          }
         }
         
결과는 4까지 출력한다. 메소드를 호출할 때 괄호에 값을 주고 있는데 저 값을 다른 값으로 바꿔보자.
메소드 numbering으 괄호 안에 위치한 숫자 5는 이 메소드가 호출될 때 limit라는 변수의 값이 된다. 
이 값은 메소드 numbering의 중괄호 안에서만 사용할 수 있다 위의 코드는 아래의 코드와 동일한 의미를 갖는다.

        public static void numbering() {
        
            int limit = 5;
            int i = 0;
            while (i< limit) {
            
            System.out.println(i);
            i++;
            }
           }

여기서 limit 라는 변수는 메소드 numbering의 정의부에 있는 로직들에게 5라는 값을 전달하고 있다. 
호출에서 입력한 값을 로직으로 매개 한다는 의미에 이러한 변수를 매개변수라고 부른다. 
영어로는 parameter다. 그리고 메소드르 호출할 때 전달된 값인 5를 '인자'영어로는 argument라고 한다.
관습적으로 매개변수와 인자를 구분하지 않고 부르는 경우 많다.


[복수의 인자]
만약 메소드로 여러개의 입력값을 전달하고 싶다면 어떻게 해야 할까? 다음의 예제는 위의 예제를 개선해서 출력할 숫자의 시작값과 마지막 값을 입력값으로 전달하는 예제다.

      public static void numbering(int init, int limit) {

          int i = init;
          
          while (i < limit) {
          
                System.out.println(i);
                i++;
                
                }
             }
             
      public static void main(String[] args) {
          numbering(1, 5);
      }
  
  결과는 1부터 4까지 출력된다. 위와 같이 입력값을 복수로 받고 싶다면 콤마 뒤에 매개변수를 정의해 주면 된다. 또 이 메소드를 호출하 때는매개변수의 순서대 인자를 배치하면 된다. 
  
  
  [return]
  
  위으 예제는 화면에 숫자를 출력한다. 물론 이것도 출력이지만 좀 더 활용독 높은 출력 방법이 있다. 아래 예제를 보자.
  
        public static String numbering(int init, int limit) {
        
        
          int i = init;  
          
          String output = "";  //만들어지는 숫자들을 output이라는 변수에 담기 위해서 변수에 빈 값을 주었다.
          
          while (i < limit) {
          
              output += i ;
              
              i++;
            }
            
         return output;
       }
       
     public static void main(String[] args) {
     
      String result = numbering(1, 5)
      
      System.out. println(result);
      }
     }
     
 메소드 내에서 사용한 return은 return 뒤에 따라오는 값을 메소드의 결과로 반환한다.
 동시에 메소드를 종료시킨다. 한가지잊지말아야할 점은 return을 통해서 반환할 값의 데이터 형식을
 메소드으 이름 앞에 명시해주어야 한다는 것이다. 
 
      public static String numbering(int init, int limit) {
      
 메소드가 리턴할 값을 명시함으로서 numbering이라는 메소드는 반드시 문자열의 값을 리턴한다는 것을 보장할 수 있는 장점이 있다.
 모든 일에는 장점과 단점이 있다. 
 
 만약에 반환값이 없다면 아래와 같이 void를 적어준다.
 
       public static void numbering(int init, int limit) {
       
       
       
   굳이 이렇게 복잡하 데이터를 리턴하는 이유는 무엇일까? 
   내용을 화면에 출력하는 것은 동일하지 않은가? 
   결론적을 말하면 부품으로서의 가치를 높이기 위해서라 할 수 있다.
   만약 내가 이 메소드가 출력한 값을 화면에 출력하는 것이 아니라 파일에 기록하고 싶다면?
   또는 이메일로 보내고 싶다면 어떻게 해야할까? 
   3개의 메소드를 만들고 용도에 따라서 코드를 재작성 하는것도 좋은 방법이다.
   하지만 더 좋은 방법은 숫자를 출력하고, 숫자를 파일에 기록하고, 숫자를 이메일로 보내는 작업으로부터
   숫자를 계산하는 로직을 분리하는 것이다. 
   numbering은 자신이 어떻게 사용될지 모른다. 
   누구든지 numbering이라는 메소드를 호출할 때 초기값과 마지막값을 입력하면 numbering은 숫자를 문자열의 형태로 반환만 하면
   되는 것이다. 코드를 보자
   
   
   
      public class MethodDemo {
      
          public static String numbering(int init, int limit) {
          
              int i = init;
              
              String output = "";
              
              while (i < limit) {
              
              output += i;
              
              i++;
              
              }
              
              return output;
              
            }
            
        puiblic static void main(String[] args) {
        
        String result = numbering(1,5);
        System.out.println(result);
        
        try {
        
            ButteredWriter out = new BufferedWriter(new FileWriter("out.txt"));
            out.write(result);
            out.close();
            
        } catch (IOException e) {
        }
       } 
   
   중요한 것은 numbering 이라는 메소드로부터 화면에 출력이라는 구체적인 행위를 제거하고 대신에 처리 결과를 반환하고 있다.
   
   return의 특성에 대해서 조금 더 알아보자. return은 값을 반환하는 동작을 한다. 그런데 이것은 return에 대한
   반쪽짜리 설명이다. return은 메소드를 중단시키는 역할도 한다. 코드를 보자
   
   
        public class ReturnDemo {
        
          public static int one() {
          
            return 1;
            return 2;
            return 3;
            
            }
            
          public static void main(String[] args) {
          
            System.out.println(one());
           }
         }
         
  위의 코드는 컴파일조차 되지 않는다. 왜냐하면 return은 메소드를 종료시키는 역할을 하므로 return이 처음 등장한 이후의 구문은 실행되지 않기 때문이다. 하지만 아래의 예제는 문제가 전혀 없다.
  
        public static String num(int i) {
        
        if (i==0) {
        
            return "zero";
            
        } else if (i==1) {
        
            return "one";
            
        } else if (i==2) {
        
            return "two";
            
        }
        return "none";
        
        }
        
        public static void main(String[] args) {
        
        System.out.println(num(1));
        
        }
        }
        
        
[복수의 리턴]

메소드는 여러 개의 입력값을 가질 수 있다. 
그렇다면 여러 개의 값을 출력하고 싶다면? 
자바는 문법적으로 그런 기능을 제공핮 않는다.
하나의 변수에 여러개의 값을 담아 출력하면 된다. 아래의 코드를 보자.

        public static String getMember1() {
        
            return "최승환";
        
        }
        public static String getMember2() {
        
            return "이소정";
        
        }        
        public static String getMember3() {
        
            return "김영진";
        
        }
        
        public static void main(String[] args) {
        
            System.out.println(getMember1());
            System.out.println(getMember2());
            System.out.println(getMember3());            
          }        
       }


하나의 메소드는 하나의 값만 반환할 수 있기 때문에 위와 같이 각각의 회원 정보를 반환하는 메소드를 만들었다. 
무언가 비정상적이지 않은가? 이번엔 배열을 이용한 아래의 코드를 보자 멤버를 담고 있는 배열을 반환하고 있다. 
간단하지 않은가 메소드 가 리턴한 배열을 멤버스에 담았다. 이변수를 이용해서 어려개의 데이터를 처리할 수 있게 된다.



    public class ReturnDemo {
    
        public static String[] getMembers() {
        
          String[] members = { "최승환", "이소정", "김영진" };
          
          return members;
          }
        
        public static void main(String[] args) {
        
              String[] members = getMembers()
              
              }
              
            }
        

          
       
 
          





























