# poker-csharp-
## 2024.10.22
名稱:撲克牌比大小
用法:
1.點開始 會啟動計時器，每0.1秒切換一次A~K的撲克牌
2.點暫停 會顯示所選到的撲克牌，且顯示結果
### 例:
![螢幕擷取畫面 2024-10-22 142713](https://hackmd.io/_uploads/SyQ6Pa4g1l.png)
![螢幕擷取畫面 2024-10-22 142825](https://hackmd.io/_uploads/Hyspw6ExJe.png)
![螢幕擷取畫面 2024-10-22 142926](https://hackmd.io/_uploads/Hk10w6Egkg.png)
### 程式碼:
```csharp
namespace WinFormsApp1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        int point;
        int pointpc;
        Random rand = new Random();
        private void button1_Click(object sender, EventArgs e)
        {
            timer1.Start();
            pointpc = rand.Next(13);
            pictureBox1.Image = imageList1.Images[pointpc];
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            label3.Text = "";
            timer1.Interval = 100;
            pictureBox1.SizeMode = PictureBoxSizeMode.Zoom;
            pictureBox2.SizeMode = PictureBoxSizeMode.Zoom;
        }

        private void button2_Click(object sender, EventArgs e)
        {
            timer1.Stop();
            if (point > pointpc)
            {
                label3.Text = "獲勝";
            }
            else if (point < pointpc)
            {
                label3.Text = "失敗";
            }
            else 
            {
                label3.Text = "平手";
            }
        }


        private void timer1_Tick(object sender, EventArgs e)
        {
            
            point = rand.Next(13);
            pictureBox2.Image = imageList1.Images[point];
        }
    }
}
```
