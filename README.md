# InterfaceLayout
package interfacelayout;

import java.awt.BorderLayout;
import java.awt.Dimension;
import java.awt.FlowLayout;
import java.awt.LayoutManager;
import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JList;
import javax.swing.JPanel;
import javax.swing.JScrollPane;
import javax.swing.JTextField;


public class Main extends JFrame {
    private JTextField textField;
    private JList<String> listView;
    private JScrollPane scrollPane;
    
    public Main() {
        super("Interfaz layout");
        this.setSize(700, 700);
        this.setLocationRelativeTo(null);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setLayout(new BorderLayout()); // Usamos BorderLayout para el marco principal
        
        JPanel miPanel = new JPanel();
        miPanel.setLayout(new FlowLayout(FlowLayout.LEFT)); // Alinea el contenido a la izquierda
        miPanel.setPreferredSize(new Dimension(300, 700)); // Tamaño preferido para este panel
        
        // Crear elementos para miPanel
        JLabel iconLabel1 = new JLabel(new ImageIcon("media/imagen.png"));
        iconLabel1.setPreferredSize(new Dimension(92, 92));
        JLabel nameLabel1 = new JLabel("MERY RONQUILLO");
        miPanel.add(iconLabel1);
        miPanel.add(nameLabel1);

        // Crear el listview (JList)
        JList<String> listView = new JList<>(new String[]{"Item 1", "Item 2", "Item 3"});
        JScrollPane scrollPane = new JScrollPane(listView); // Para tener barras de desplazamiento si es necesario
        scrollPane.setPreferredSize(new Dimension(400, 300)); // Tamaño preferido para el scrollPane

        // Crear el textfield (JTextField)
        JTextField textField = new JTextField(20);
        textField.setPreferredSize(new Dimension(400, 50)); // Tamaño preferido para el textfield

        // Agregar el scrollPane y el textField al marco principal
        this.add(scrollPane, BorderLayout.CENTER); // Agregar scrollPane al centro
        this.add(textField, BorderLayout.SOUTH); // Agregar textField al borde inferior
        this.add(miPanel, BorderLayout.WEST); // Agregar miPanel a la izquierda
        
        this.setVisible(true); // Hacer visible el marco
    }

    public static void main(String[] args) {
        new Main(); // Crear una instancia de la clase Main para mostrar la interfaz
    }
}

