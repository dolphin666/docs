### 文本模块  <!-- {docsify-ignore} -->

1. #### 字符串

   ![image-20230302175050442](func04.assets/image-20230302175050442.png) 

   示例 1：

   定义"hello world"字符串

   ![image-20230302175100451](func04.assets/image-20230302175100451.png) 

   ```c
   "hello world"
   ```

2. #### 字符

   ![image-20230302175333645](func04.assets/image-20230302175333645.png) 

   示例 1：

   定义'A'字符

   ![image-20230302175342707](func04.assets/image-20230302175342707.png) 

   ```c
   'A'
   ```

   定义'\n'换行符

   ![image-20230302175910343](func04.assets/image-20230302175910343.png) 

   ```c
   '\n'
   ```

3. #### 连接文本或转文本

   ![image-20230303084903159](func04.assets/image-20230303084903159.png) 

   示例 1：
   ![image-20230302180001372](func04.assets/image-20230302180001372.png)

   ```cpp
   #include <CH32V103.h>
   #include "myLib/CH32V_ST7735S.h"
   
   SPITFT spi_tft(128,128,PC5,PA2,PA4);
   
   int main(void)
   {
     CH32_Init();
     spi_tft.init();
     spi_tft.set_direction(2);
     spi_tft.clear((0xFFFF));
     spi_tft.set_cursor(0,0);
     spi_tft.draw_hanzi_12((String("好好") + String("搭搭")));
     while(1){
       
     }
     return 1;
   }
   ```
   彩屏显示"好好搭搭"。

4. #### 获取字符串长度

   ![image-20230303090317173](func04.assets/image-20230303090317173.png) 

   示例 1：

   ![image-20230303090338700](func04.assets/image-20230303090338700.png) 

   ```cpp
   #include <CH32V103.h>
   #include "myLib/CH32V_ST7735S.h"
   #include <string.h>
   
   SPITFT spi_tft(128,128,PC5,PA2,PA4);
   
   int main(void)
   {
     CH32_Init();
     spi_tft.init();
     spi_tft.set_direction(2);
     spi_tft.clear((0xFFFF));
     spi_tft.set_cursor(0,0);
     spi_tft.print((String("abc").length()));
     while(1){
   		
     }
     return 1;
   }
   ```

   彩屏显示 3

5. #### 文本转整数

   ![image-20230303091039633](func04.assets/image-20230303091039633.png) 

   示例 1：

   ![image-20230303091147323](func04.assets/image-20230303091147323.png) 

   ```cpp
   #include <CH32V103.h>
   #include "myLib/CH32V_ST7735S.h"
   
   SPITFT spi_tft(128,128,PC5,PA2,PA4);
   
   int main(void)
   {
     CH32_Init();
     spi_tft.init();
     spi_tft.set_direction(2);
     spi_tft.clear((0xFFFF));
     spi_tft.set_cursor(0,0);
     spi_tft.print((String("123").toInt()));
     while(1){
   		
     }
     return 1;
   }
   ```

   彩屏显示 123

6. #### 转文本

   ![image-20230303135053222](func04.assets/image-20230303135053222.png) 

   示例 1：

   ![image-20230303135352555](func04.assets/image-20230303135352555.png) 

   ```cpp
   #include <CH32V103.h>
   #include "myLib/CH32V_ST7735S.h"
   
   SPITFT spi_tft(128,128,PC5,PA2,PA4);
   
   int main(void)
   {
     CH32_Init();
     spi_tft.init();
     spi_tft.set_direction(2);
     spi_tft.clear((0xFFFF));
     spi_tft.set_cursor(0,0);
     spi_tft.draw_hanzi_12((String(456)));
     while(1){
       
     }
     return 1;
   }
   ```

   彩屏显示 456。



7. #### 查找文本位置

   ![image-20230327153722401](func04.assets/image-20230327153722401.png) 

   

8. #### 提取文本

   ![image-20230327153656450](func04.assets/image-20230327153656450.png) 