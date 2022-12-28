> 정리

<br>

- 자바에서는 클래스 안에 클래스가 들어갈 수 있다. 이러한 클래스를 Nested Class라고 한다.
    - 존재 이유는 코드의 간결성을 위함이다.

- Nested Class
    - Static nested class (static을 사용한 클래스)
        - 클래스를 묶어 용도를 명확하게 하기 위해 사용한다.
        - 겉으로 보기엔 유사하나, 내부적으로 구현이 달라야 하는 경우에 쓰인다.
        
        ```
        public class University() {
            static class Student{
        
            }
        }
        
        public class School() {
            static class Student{
        
            }
        }
        ```
        
    - inner class
        - Local inner class (내부 클래스)
            - 먼저 외부 클래스의 객체를 만들고, 그 객체를 이용해서 
            내부 클래스의 객체를 만드는 방식이다.
            - 일반적으로 내부 구현을 감추고 싶을 때 사용한다.
            
            ```
            public class Test {
            
                public class OuterOfInner {
                    class Inner {
                        private int value = 0;
            
                        public int getValue() {
                            return value;
                        }
            
                        public void setValue(int value) {
                            this.value = value;
                        }
                    }
                }
            
                public static void main(String[] args) {
                    Test innerTest = new Test();
                    innerTest.makeInnerObject();
                }
            
                public void makeInnerObject() {
                    // 먼저 외부 클래스의 객체를 만든다.
                    OuterOfInner outer = new OuterOfInner();
                    // 외부 클래스의 객체를 이용해서 내부 클래스의 객체를 만든다.
                    OuterOfInner.Inner inner = outer.new Inner();
                    // 이렇게 내부 클래스를 이용하는 이유는 캡슐화 때문이다.
                    // == 내부 구현을 감추고 싶기 때문이다.
                    inner.setValue(20);
                    System.out.println("inner.getValue() : " + inner.getValue());
                }
            }
            ```
            
        - Anonymous inner class (익명 클래스)
            - 내부 클래스와 비슷하나, 이름이 없는 클래스
            - 클래스의 선언과 객체의 생성을 동시에 하는 이름없는 클래스
            - `AnonymousSample`
                
                ```
                package com.yang.app;
                
                public class AnonymousSample {
                    public static void main(String[] args) {
                        AnonymousSample ex = new AnonymousSample();
                
                        ex.setButtonListenerWithNoAnonymous();
                        ex.setButtonListenerWithAnonymous();
                        ex.setButtonListenerWithObject();
                    }
                
                    public void setButtonListenerWithNoAnonymous() {
                        System.out.println("With outer class that implements EventListener");
                        MagicButton button = new MagicButton();
                        MagicButtonListener listener = new MagicButtonListener();
                        button.setListener(listener);
                        button.onClickProcess();
                        System.out.println();
                    }
                
                    public void setButtonListenerWithAnonymous() {
                        System.out.println("With Anonymous class");
                        MagicButton button = new MagicButton();
                        button.setListener(new EventListener() {
                            public void onClick() {
                                System.out.println("Magic Button clicked!! with Anonymous class");
                            }
                        });
                        button.onClickProcess();
                        System.out.println();
                    }
                
                    public void setButtonListenerWithObject() {
                        System.out.println("With object that implements EventListener");
                        MagicButton button = new MagicButton();
                        EventListener listener = new EventListener() {
                            public void onClick() {
                                System.out.println("Magic button clicked with object");
                            }
                        };
                        button.setListener(listener);
                        button.onClickProcess();
                        System.out.println();
                    }
                }
                
                ```
                
            - `EventListener`
                
                ```
                package com.yang.app;
                
                public interface EventListener {
                    public void onClick();
                }
                
                ```
                
            - `MagicButton`
                
                ```
                package com.yang.app;
                
                public class MagicButton {
                    private EventListener listener;
                
                    public void setListener(EventListener listener) {
                        this.listener = listener;
                    }
                    public void onClickProcess(){
                        if (listener != null) {
                            listener.onClick();
                        }
                    }
                }
                
                ```
                
            - `MagicButtonListener`
                
                ```
                package com.yang.app;
                
                public class MagicButtonListener implements EventListener {
                
                    public void onClick() {
                        System.out.println("Magic Button Clicked");
                    }
                }
                
                ```
