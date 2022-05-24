package arraylist;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class LeitorPreços {
    public static void main(String[] args) {
    System.out.println("#### Média de Preços ####");
    
    String produto;
    List<Integer> precoPorMes;
    
    try (Scanner entrada = new Scanner (System.in)){
        System.out.println("Informe o nome do produto: ");
        produto = entrada.nextLine();
        
        String continuar;
        System.out.println("Gostaria de adicionar os preços correspondentes ao produto? (s/n)");
        continuar = entrada.nextLine();
        
        int mes = 1;
        precoPorMes = new ArrayList<>();
        
        while("s".equalsIgnoreCase(continuar)){
            System.out.println("Qual o preço do produto correspondente ao mes " + mes + "?");
            int precoNoMes = entrada.nextInt();
            precoPorMes.add(precoNoMes);
            
            mes = mes + 1;
            
            System.out.print("Deseja continuar? (s/n):");
            continuar = entrada.next();
        }
    }
    
    imprimirMediaDePrecos(produto, precoPorMes);
    
  }
  private static void imprimirMediaDePrecos(String produto, List<Integer> precoPorMes){
      double totalPrecos = 0;
      for (Integer precoNoMes : precoPorMes){
          totalPrecos += precoNoMes;
      }
      
      double media = totalPrecos/precoPorMes.size();
      
      System.out.print("A media e: " + media);
  }
}
