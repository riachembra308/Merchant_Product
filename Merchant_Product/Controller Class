package org.jsp.merchant_product_app.controller;

import java.util.List;
import java.util.Scanner;

import org.jsp.merchant_product_app.dao.MerchantDao;
import org.jsp.merchant_product_app.dao.ProductDao;
import org.jsp.merchant_product_app.dto.Merchant;
import org.jsp.merchant_product_app.dto.Product;

public class Merchant_Product_Controller {

	static Scanner sc=new Scanner(System.in);
	static MerchantDao mdao= new MerchantDao();
	static ProductDao pdao= new ProductDao();
	public static void main(String[] args) {
		while(true)
		{
			System.out.println("1. Save Merchant");
			System.out.println("2. Update Merchant");
			System.out.println("3. Find Merchant by Id");
			System.out.println("4. Find Merchant by Product Id");
			System.out.println("5. Find Merchant by Product name");
			
			System.out.println("6. Add product");
			System.out.println("7. Update product");
			System.out.println("8. Find Product by Id");
			System.out.println("9. Find Product by Merchant Id");
			System.out.println("10. Find Product by Merchant name and password");
			
			System.out.println("Enter your choice");
			int choice=sc.nextInt();
			sc.nextLine();
			switch(choice)
			{
			case 1: {saveMerchant();
			        break;}
			case 2: {updateMerchant();
	                break;}
			case 3: {findMerchantById();
	                break;}
			case 4: {findMerchantByProductId();
	                break;}
			case 5: {findMerchantByProductName();
	                break;}
			case 6: {addProduct();
	                break;}
			case 7: {updateProduct();
	                break;}
			case 8: {findProductById();
	                break;}
			case 9: {findProductByMerchantId();
	                break;}
			case 10: {findProductByMerchantNameAndPassword();
	                break;}
			}
		}
	}
	public static void addProduct()
	{
       System.out.println("Enter the merchant id: ");
       int mid=sc.nextInt();
       System.out.println("Enter the product info: (Name, Brand, Category, Price)");
       Product p=new Product();
       sc.nextLine();
       p.setName(sc.nextLine());
       p.setBrand(sc.nextLine());
       p.setCategory(sc.nextLine());
       p.setPrice(sc.nextDouble());
       
       Product pdb=pdao.addProduct(mid,p);
       if(pdb!=null)
       {
    	   System.out.println("Product with id "+pdb.getId()+" is added to the Merchant");
       }
       else
       {
    	   System.out.println("No record found");
       }
       }
	public static void updateMerchant()
	{
		System.out.println("Enter the merchant info (id, name, gst_num, email, phone_num, password) ");
		Merchant m= new Merchant();
		sc.next();
		m.setId(sc.nextInt());
		m.setName(sc.next());
		m.setGst_num(sc.next());
		m.setEmail(sc.next());
		m.setPhone(sc.nextLong());
		m.setPassword(sc.next());
		
		Merchant mdb=mdao.updateMerchant(m);
		if(mdb!=null)
		{
			System.out.println("Merchant is updated with id: "+mdb.getId());
		}
		else
		{
			System.out.println("No record found");
		}
	}
	
	public static void saveMerchant()
	{
		System.out.println("Enter the merchant info (id, name, gst_num, email, phone_num, password) ");
		Merchant m= new Merchant();
		
		m.setName(sc.next());
		m.setGst_num(sc.next());
		m.setEmail(sc.next());
		m.setPhone(sc.nextLong());
		m.setPassword(sc.next());
		
		Merchant mdb= mdao.saveMerchant(m);
		System.out.println("Merchant with id: "+mdb.getId()+" is inserted");
	}
	
	public static void findMerchantById() {

	    System.out.println("Enter merchant id:");

	    int id = sc.nextInt();

	    Merchant mdb = mdao.findMerchantById(id);

	    if (mdb != null) {
	        System.out.println(mdb);
	    } 
	    else {
	        System.out.println("No record found");
	    }
	}
	
	public static void findMerchantByProductId() {

	    System.out.println("Enter product id:");

	    int pid = sc.nextInt();

	    Merchant mdb = mdao.findMerchantByProductId(pid);

	    if (mdb != null) {
	        System.out.println(mdb);
	    }
	    else {
	        System.out.println("No record found");
	    }
	}
	
	public static void findMerchantByProductName() {

	    System.out.println("Enter product name:");
	    String pname = sc.nextLine();

	    Merchant mdb = mdao.findMerchantByProductName(pname);

	    if (mdb != null) {
	        System.out.println(mdb);
	    }
	    else {
	        System.out.println("No record found");
	    }
	}
	
	public static void updateProduct() {

	    System.out.println("Enter product info (id, name, brand, category, price):");

	    Product p = new Product();
       
	    p.setId(sc.nextInt());
	    sc.nextLine();
	    p.setName(sc.nextLine());
	    p.setBrand(sc.nextLine());
	    p.setCategory(sc.nextLine());
	    p.setPrice(sc.nextDouble());

	    Product pdb = pdao.updateProduct(p);

	    if (pdb != null) {
	        System.out.println("Product is updated with id: " + pdb.getId());
	    }
	    else {
	        System.out.println("No record found");
	    }
	}
	
	public static void findProductById() {

	    System.out.println("Enter product id:");
	    int id = sc.nextInt();

	    Product pdb = pdao.findProductById(id);

	    if (pdb != null) {
	        System.out.println(pdb);
	    }
	    else {
	        System.out.println("No record found");
	    }
	}
	
	public static void findProductByMerchantId() {

	    System.out.println("Enter merchant id:");
	    int mid = sc.nextInt();

	    List<Product> products = pdao.findProductByMerchantId(mid);

	    if (!products.isEmpty()) {

	        for (Product p : products) {
	            System.out.println(p);
	        }

	    }
	    else {
	        System.out.println("No record found");
	    }
	}
	
	public static void findProductByMerchantNameAndPassword() {

	    System.out.println("Enter merchant name:");
	    String name = sc.next();

	    System.out.println("Enter merchant password:");
	    String password = sc.next();

	    List<Product> products =
	            pdao.findProductByMerchantNameAndPassword(name, password);

	    if (!products.isEmpty()) {

	        for (Product p : products) {
	            System.out.println(p);
	        }

	    }
	    else {
	        System.out.println("No record found");
	    }
	}

}
