/*
 Sanyerlis Camacaro 10/03/2022 - CSC202 - Startup Company - Moms Talk Crypto Employee Page - add classes including inheritance- Sancamac@uat.edu
Log: As of September 29st, 2022 I believe this project will take me to complete in less than 4 hours splitted in 2 days.
On 09/29/2022 I started watching Wednesday class to follow along and I started on this assignment around 11:30pm until 1:30am 9/30/2022.

To Complete this StartUp Company Employee Page I've expected to complete the project within 2 days in total of 4 hours. In total I took 1 day and I completed this assignment in 2 hours.
I believe that it took longer than I've expected because I had to watch the class video and follow along.
Next time, I will try to organize myself better with home responsabilities and rewatch the classes ahead of time and ask questions when it's needed. 
 */
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Live_Class_092622_Notes
{
    public partial class Form1 : Form
    {
        class employee
        {// attributes
            protected string fname;
            protected string lname;

            public employee(string fn, string ln)
            {
                this.fname = fn;
                this.lname = ln;
                MessageBox.Show("New Employee");
            }
            public void display()
            {
                MessageBox.Show(" Employee Full Name: " + this.fname + ' ' + this.lname);
            }

            public string getfn()
            { return this.fname; }

            public void setfn(string fn)
            {
                this.fname = fn;
            }
        }
        class FT:employee
        {
            //attributes
            private double salary;

            public FT(string fn, string ln, double sal):base(fn,ln)
            {
                this.salary = sal;
            }

            public void displayFT()
            {
                base.display();
                MessageBox.Show(" Full Time Employee Salary: " + this.salary.ToString());
            }
        }

        class PT: employee
        {
            //attributes
            private int hoursWorked;

            public PT(string fn, string ln, int hw ) : base(fn,ln)
            {

                this.hoursWorked = hw;
            }
            public void displayPT()
            {
                base.display();
                MessageBox.Show("Part-Time Employee Hourly Pay: " + this.hoursWorked.ToString());
            }
        }
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            employee e1 = new employee(textBox1.Text, textBox2.Text);
            e1.display();
            
        }

        private void button2_Click(object sender, EventArgs e)
        {
            textBox3.Visible = true;
            MessageBox.Show("Full-Time Employee");
            double sal = double.Parse(textBox3.Text);
            FT f1 = new FT(textBox1.Text, textBox2.Text, sal);
            f1.displayFT();
        }

        private void button3_Click(object sender, EventArgs e)
        {
            MessageBox.Show("Part-Time Employee");
            int hw = int.Parse(textBox3.Text);
            PT P1 = new PT(textBox1.Text, textBox2.Text, hw);
            P1.displayPT();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void button4_Click(object sender, EventArgs e)
        {
            MessageBox.Show("Welcome To Moms Talk Crypto Company Employee Page!");
        }
    }
}
