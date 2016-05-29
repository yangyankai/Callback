# Callback
自定义回调

//A使用B里面的回掉

A:
B b=new B();
//方法1，直接赋值
b.icallBack = new NeedOrderAdapter.ICoallBack() {
            @Override
            public void onClickButton(String s) {
                Log.e("TAG", "onClickButton: " + s);
            }
        };

//方法2，通过set赋值
//  adapter.setonClick(new NeedOrderAdapter.ICoallBack() {
//            @Override
//            public void onClickButton(String s) {
//                Log.e("TAG", "onClickButton: "+s );
//            }
//        });

B:

 //1. 一定一个接口(和里面的方法) 
    
    public interface ICoallBack{  
        public void onClickButton(String s);  
    }  
      
//2. 初始化接口变量（可设置为public直接赋值,也可以通过set方法）   
 public   ICoallBack icallBack = null; 
//    public void setonClick(ICoallBack iBack)  
//    {  
//        icallBack = iBack;  
//    } 

//3. 把计算的值回掉给A    
icallBack.onClickButton("value");  
