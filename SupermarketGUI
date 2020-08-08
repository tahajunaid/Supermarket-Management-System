package supermarketgui;
import java.awt.*;
import java.awt.event.*;
import java.awt.Color;
import javax.swing.*;
import javax.swing.table.*;
import java.sql.*;
import java.util.Calendar;
import java.util.logging.Level;
import java.util.logging.Logger;
import net.proteanit.sql.DbUtils;
public class SupermarketGUI extends Frame implements ActionListener {
    Label l1;
    TextField name,pass;
    Button b1,b2;
    String msg="";
   
    Connection con;
 
    SupermarketGUI(){
        addWindowListener(new WindowAdapter() {
         @Override
         public void windowClosing(WindowEvent windowEvent){
           dispose();
         }        
      });
        setLayout(new FlowLayout());
        this.setLayout(null);
        Label n=new Label("Id:",Label.RIGHT);
        Label p=new Label("password:",Label.RIGHT);
        l1=new Label("Welcome to Taha's Supermarket");
        l1.setBounds(100, 45, 300, 40);
        add(l1);
        name=new TextField(20);
        pass=new TextField(20);
        pass.setEchoChar('*');
        b1=new Button("login");
        b2=new Button("cancel");
        this.add(n);
        this.add(name);
        this.add(p);
        this.add(pass);
        this.add(b1);
        this.add(b2);
        n.setBounds(70,100,90,60);
        p.setBounds(70,140,90,60);
        name.setBounds(200,117,90,20);
        pass.setBounds(200,157,90,20);
        b1.setBounds(120,260,70,40);
        b2.setBounds(200,260,70,40);
        setVisible(true);
        setSize(400,400);
        setTitle("Supermarket GUI");
        String pass;
        b1.addActionListener(this);
b2.addActionListener(this);  

try
{
    con=DriverManager.getConnection("jdbc:oracle:thin:@localhost:1522:mydatab","scott","tiger");
}
catch(SQLException e)
{
    System.out.println(e);
}

}
    public static void main(String[]args)
    {
        new SupermarketGUI();
    }
   
    @Override
    public void actionPerformed(ActionEvent e) {
       String s= e.getActionCommand();
       if(s.equals("login"))
     { if(( name.getText().equals("aaa"))&&(pass.getText().equals("aaa")))
       { meth();msg="";repaint();}
      else
           {  msg="Invalid Credential";
             repaint();}}
       if(s.equals("cancel"))
           dispose();
           
           }
public void paint(Graphics g){
               g.drawString(msg,170,360);
    }
public void meth() {
    setVisible(false);
    JFrame f1 = new JFrame("Cashier Billing Menu");
    f1.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
    JMenuBar mb=new JMenuBar();  
     
         JMenu file=new JMenu("Account");
         JMenu edit=new JMenu("Help");
         JMenu view=new JMenu("Settings");
         JMenuItem m1=new JMenuItem("Details");
         JMenuItem m2=new JMenuItem("Edit");
          JMenuItem m3=new JMenuItem("Requests");
          JMenuItem m4=new JMenuItem("Logout");
          m4.addActionListener(new ActionListener(){public void actionPerformed(ActionEvent e){f1.dispose();setVisible(true);msg="Logged Out";repaint();}});
          file.add(m1);
          file.add(m2);
          file.add(m3);
          file.add(m4);
         mb.add(file);
         mb.add(edit);
         mb.add(view);
         f1.setJMenuBar(mb);
   Checkbox mem=new Checkbox("Member");
    mem.setBounds(280,50,70,20);
    f1.add(mem);
    JLabel l1,l2,l3,l4,l5,l6,l7;
    JButton total;
    JTextField t1,t2,t3,t4,t5,t6,t7,t8,t9,t10,t11,t12;
    l1=new JLabel("Customer Details :");
    l2=new JLabel("Name");l3=new JLabel("Phone");
    l4=new JLabel("Cart :");
    l5=new JLabel("Item");l6=new JLabel("Quantity");l7=new JLabel("Price/unit");
    total=new JButton("Total :");
    l1 .setBounds(30,20,150,15);
    l2 .setBounds(30,40,80,15);l3 .setBounds(180,40,40,15);
    l4 .setBounds(30,100,40,15);
    l5 .setBounds(30,120,40,15);l6 .setBounds(150,120,60,15);l7 .setBounds(280,120,90,15);
    total.setBounds(110,300,70,20);
     f1.add(l1);f1.add(l2);f1.add(l3);f1.add(l4);f1.add(l5);f1.add(l6);f1.add(l7);f1.add(total);
     
    t1=new JTextField();t2=new JTextField();
    t3=new JTextField();t4=new JTextField();t5=new JTextField();
    t6=new JTextField();t7=new JTextField();t8=new JTextField();
    t9=new JTextField();t10=new JTextField();t11=new JTextField();
    t12=new JTextField();
    t1.setBounds(30,60,100,20); t2.setBounds(180,60,80,20);
    t3.setBounds(30,140,100,20);t4.setBounds(150,140,100,20);t5.setBounds(280,140,50,20);
    t6.setBounds(30,180,100,20);t7.setBounds(150,180,100,20);t8.setBounds(280,180,50,20);
    t9.setBounds(30,220,100,20);t10.setBounds(150,220,100,20);t11.setBounds(280,220,50,20);
    t12.setBounds(200,300,70,20);
    f1.add(t1);f1.add(t2);f1.add(t3);f1.add(t4);f1.add(t5);f1.add(t6);f1.add(t7);f1.add(t8);f1.add(t10);f1.add(t9);f1.add(t11);f1.add(t12);
    total.addActionListener(new ActionListener()
{
@Override
public void actionPerformed(ActionEvent event)
{int tot=Integer.parseInt(t5.getText())*Integer.parseInt(t4.getText())+Integer.parseInt(t8.getText())*Integer.parseInt(t7.getText())+Integer.parseInt(t11.getText())*Integer.parseInt(t10.getText());
if(mem.getState())
    tot=(int) (tot-0.05*tot);
t12.setText("$ "+String.valueOf(tot));
 
}
});
Button stock = new Button("Stock");
stock.setBackground(Color.CYAN);
stock.addActionListener(new ActionListener()
{
@Override
public void actionPerformed(ActionEvent event)
{
JFrame guiFrame = new JFrame();

guiFrame.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
guiFrame.setTitle("Supermarket Stock");
guiFrame.setSize(300,250);

guiFrame.setLocationRelativeTo(null);

String[] fruitOptions = {"Apple", "Apricot", "Banana"
        ,"Cherry", "Date", "Kiwi", "Orange", "Pear", "Strawberry"};

String[] vegOptions = {"Asparagus", "Beans", "Broccoli", "Cabbage"
, "Carrot", "Celery", "Cucumber", "Leek", "Mushroom"
, "Pepper", "Radish", "Shallot", "Spinach", "Swede"
, "Turnip"};

final JPanel comboPanel = new JPanel();
JLabel comboLbl = new JLabel("Fruits:");
JList fruits = new JList(fruitOptions);
fruits.setLayoutOrientation(JList.HORIZONTAL_WRAP);
comboPanel.add(comboLbl);
comboPanel.add(fruits);
final JPanel listPanel = new JPanel();
listPanel.setVisible(false);
JLabel listLbl = new JLabel("Vegetables:");
JList vegs = new JList(vegOptions);
vegs.setLayoutOrientation(JList.HORIZONTAL_WRAP);
listPanel.add(listLbl);
listPanel.add(vegs);
JButton vegFruitBut = new JButton( "Fruit or Veg");
vegFruitBut.addActionListener(new ActionListener()
{
@Override
public void actionPerformed(ActionEvent event)
{
listPanel.setVisible(!listPanel.isVisible());
comboPanel.setVisible(!comboPanel.isVisible());
}
});
guiFrame.add(comboPanel, BorderLayout.NORTH);
guiFrame.add(listPanel, BorderLayout.CENTER);
guiFrame.add(vegFruitBut,BorderLayout.SOUTH);

guiFrame.setVisible(true);
}
});
Button sales = new Button("Sales");
sales.setBackground(Color.CYAN);


sales.addActionListener(new ActionListener()
{
@Override
public void actionPerformed(ActionEvent event)
{
JFrame guiFrame = new JFrame();
guiFrame.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
guiFrame.setTitle("Sales");
guiFrame.setSize(700,200);
guiFrame.setLocationRelativeTo(null);

JTable table = new JTable(new ExampleTableModel());

table.setAutoCreateRowSorter(true);
JScrollPane tableScrollPane = new JScrollPane(table);
guiFrame.add(tableScrollPane);
guiFrame.setVisible(true);

String query="select * from sales";
   try {
PreparedStatement ps=con.prepareStatement(query);
 ResultSet rs=ps.executeQuery();
 table.setModel(DbUtils.resultSetToTableModel(rs));
 
   }
   catch (SQLException e)
   {
       System.out.println(e);
    }
}
    }
);
Button checkout = new Button("Checkout");
checkout.setBackground(Color.PINK);
checkout.addActionListener(new ActionListener()
{
@Override
public void actionPerformed(ActionEvent event)
{ JOptionPane.showMessageDialog(null,"Thanks for Shopping ...Visit again !","Payment Succesfull",1);
try{
Class.forName("oracle.jdbc.OracleDriver");
Connection con=DriverManager.getConnection("jdbc:oracle:thin:@localhost:1522:mydatab","scott","tiger");
Calendar calendar = Calendar.getInstance();
java.sql.Date sdate = new java.sql.Date(calendar.getTime().getTime());
String query;
query="insert into sales values(?,?,?,?,?,?,?,?,?,?,?,?,?)";
PreparedStatement ps=con.prepareStatement(query);

ps.setString(1, t1.getText());
ps.setInt(2, Integer.parseInt(t2.getText()));
ps.setDate(3, sdate);
ps.setString(4, t3.getText());
ps.setInt(5, Integer.parseInt(t4.getText()));
ps.setInt(6, Integer.parseInt(t5.getText()));
ps.setString(7, t6.getText());
ps.setInt(8, Integer.parseInt(t7.getText()));
ps.setInt(9, Integer.parseInt(t8.getText()));
ps.setString(10, t9.getText());
ps.setInt(11, Integer.parseInt(t10.getText()));
ps.setInt(12, Integer.parseInt(t11.getText()));
ps.setString(13, t12.getText());
ps.execute();

JOptionPane.showMessageDialog(null,"data inserted Successfully!");
dispose();
con.close();
}
     
catch(ClassNotFoundException|SQLException e)
   {  
                  System.out.println(e);            
    }
}
});
stock.setBounds(380,70,70,30);
sales.setBounds(380,140,70,30);
checkout.setBounds(380,280,80,50);


f1.add(stock);f1.add(sales);f1.add(checkout);
f1.setLayout(null);
f1.setSize(500,400);
f1.setVisible(true);
    }
public class ExampleTableModel extends AbstractTableModel{

String[] columnNames = {"Sl.No", "Item", "Customer", "Quantity","Time" };
Object[][] data = {
{1, "Apples", "Michael",5 , "10:00 am" },
{2, "Carrot", "Michael",  12, "10:01 am"},
{3, "Brocolli", "Michael", 2, "10:01 am"},
{4, "Apple", "Kiran",  4, "10:22 am" },
{5, "Celery", "Kiran",  2, "10:22 am"},
{6, "Cucumber", "Sakshi",  10, "11:46 am" },
{7, "Date", "Manish",  32, "1:43 pm"},
{8, "Mango", "Minish",  6, "1:44 pm"  },
{9, "Mushroom", "Manish",  11, "1:44 pm" },
{10, "Strawberry", "Anand", 15, "1:50 pm"},
};
@Override
public int getRowCount()
{
return data.length;
}
@Override
public int getColumnCount()
{
return columnNames.length;
}
@Override
public Object getValueAt(int row, int column)
{
return data[row][column];
}
//Used by the JTable object to set the column names
@Override
public String getColumnName(int column) {
return columnNames[column];
}

@Override
public Class getColumnClass(int c) {
return getValueAt(0, c).getClass();
}

}
}
