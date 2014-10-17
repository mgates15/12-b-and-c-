12-b-and-c-
===========
b) The code is the following:

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Morning extends JFrame
implements ActionListener
{
	private EasySound rooster;
	private int time;
  

  public Morning()
   {
    super("Morning");
    rooster = new EasySound("roost.wav");
    
    Container c = getContentPane();
    c.setBackground(Color.WHITE);
 
    time = 0;
    Timer clock = new Timer(5000, this); 
    clock.start();
}

  public void playSound()
  {
	  int m = 120*((time % 2) +1);
	  if (m <= 120)
	  {
		  rooster.play();
	  }
  }
  public void actionPerformed (ActionEvent m)
  {
	  time++;
	  if (time % 2 == 0) rooster.play();
	  repaint(0);
  }
  /**
   *   Constructor
   */

  public static void main(String[] args)
  {
    Morning morning = new Morning();
    morning.setSize(300, 150);
    morning.setDefaultCloseOperation(EXIT_ON_CLOSE);
    morning.setVisible(true);
  }
}  

(c) The code is the following:

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Morning extends JFrame
implements ActionListener
{
	private EasySound rooster;
	private EasySound moo;
	private int time;
  

  public Morning()
   {
    super("Morning");
    rooster = new EasySound("roost.wav");
    rooster = new EasySound("moo.wav");
    
    
    if (time % 3 == 0) {
      rooster.play();
      Container c = getContentPane();
      c.setBackground(Color.WHITE);
   }
   
   else {
      moo.play();
      Container c = getContentPane();
      c.setBackground(Color.BLACK);
 
    time = 0;
    Timer clock = new Timer(5000, this); 
    clock.start();
   }
   repaint();
}

  public static void main(String[] args)
  {
    Morning morning = new Morning();
    morning.setSize(300, 150);
    morning.setDefaultCloseOperation(EXIT_ON_CLOSE);
    morning.setVisible(true);
  }
}  
