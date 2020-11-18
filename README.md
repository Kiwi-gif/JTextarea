# JTextarea

package textareaframe;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.Box;
import javax.swing.JFrame;
import javax.swing.JTextArea;
import javax.swing.JButton;
import javax.swing.JScrollPane;
public class TextAreaFrame extends JFrame 
{
  private JTextArea textArea1;
  private JTextArea textArea2;
  private JButton copyJButton;
 
  
  public TextAreaFrame()
  {
      super("Texto em area");
      Box box = Box.createHorizontalBox();
      String demo = "Essa é a String \n" + 
       "Copie texto\nPara um text nessa area\n"+
       "Outro texto\n Evento Teclado\n";
      
      textArea1 = new JTextArea(demo, 10, 15);
      box.add(new JScrollPane(textArea1));
      
      copyJButton = new JButton("Copiar >>>");
      box.add(copyJButton);
      copyJButton.addActionListener(new ActionListener()
              {
      public void actionPerformed(ActionEvent event)
      {
        textArea2.setText(textArea1.getSelectedText());  
      }
      }
      );
      
      JButton bt_limpar = new JButton("Limpar");
    bt_limpar.setBounds(155, 95, 95, 25);
    this.add(bt_limpar);
 
      
      textArea2 = new JTextArea(10,15);
      textArea2.setEditable(false);
      box.add(new JScrollPane(textArea2));
      add(box);
  }
  
     
    public static void main(String[] args) 
    {
       TextAreaFrame textAreaFrame = new TextAreaFrame();
       textAreaFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
       textAreaFrame.setSize(425,200);
       textAreaFrame.setVisible(true);
    }
}
