# WalkerFinal

package Walker;



	
	import java.awt.FlowLayout;
	import java.awt.event.*;
	import java.io.File;
	import javax.swing.*;

	public class MyFrame extends JFrame implements ActionListener{

		/**
		 * 
		 */
		private static final long serialVersionUID = 1L;
		JButton button;
		
		MyFrame(){		
			this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
			this.setLayout(new FlowLayout());
			
			button = new JButton("Selecionar Pasta");
			button.addActionListener(this);
			
			this.add(button);
			this.pack();
			this.setVisible(true);
		}
		
		@Override
		public void actionPerformed(ActionEvent e) {
			
			if(e.getSource()==button) {
				
				JFileChooser fileChooser = new JFileChooser();
				
				fileChooser.setCurrentDirectory(new File(".")); //definir o diretorio atual
				int response = fileChooser.showOpenDialog(null); //selecione o arquivo para abrir
				//int response = fileChooser.showSaveDialog(null); //selecione o arquivo para salvar
				
				if(response == JFileChooser.APPROVE_OPTION) {
					File file = new File(fileChooser.getSelectedFile().getAbsolutePath());
					System.out.println(file);
				}
			}
		}
	}
