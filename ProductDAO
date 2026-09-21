package org.jsp.merchant_product_app.dao;

import java.util.List;

import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.EntityTransaction;
import javax.persistence.Persistence;

import org.jsp.merchant_product_app.dto.Merchant;
import org.jsp.merchant_product_app.dto.Product;

public class ProductDao {
	EntityManagerFactory emf=Persistence.createEntityManagerFactory("dev");
	EntityManager em=emf.createEntityManager();
	public Product addProduct(int mid, Product p)
	{
		EntityTransaction etran=em.getTransaction();
		etran.begin();
		Merchant mdb=em.find(Merchant.class, mid);
		if(mdb!=null)
		{
			p.setM(mdb);
			List<Product> p1=mdb.getP_list();
			p1.add(p);
			em.persist(p);
			etran.commit();
			return p;
		} 
			else {
			    etran.rollback();
			    return null;
			}
	}
	
	public Product updateProduct(Product p) {

	    EntityTransaction etran = em.getTransaction();
	    etran.begin();

	    Product pdb = em.find(Product.class, p.getId());

	    if (pdb != null) {

	        pdb.setName(p.getName());
	        pdb.setBrand(p.getBrand());
	        pdb.setCategory(p.getCategory());
	        pdb.setPrice(p.getPrice());

	        etran.commit();
	        return pdb;
	    }
	    else {
	        etran.rollback();
	        return null;
	    }
	}
	
	public Product findProductById(int id) {
	    return em.find(Product.class, id);
	}
	
	public List<Product> findProductByMerchantId(int mid) {

	    return em.createQuery(
	            "select p from Product p where p.m.id=?1",
	            Product.class)
	            .setParameter(1, mid)
	            .getResultList();
	}
	
	public List<Product> findProductByMerchantNameAndPassword(String name, String password) {

	    return em.createQuery(
	            "select p from Product p where p.m.name=?1 and p.m.password=?2",
	            Product.class)
	            .setParameter(1, name)
	            .setParameter(2, password)
	            .getResultList();
	}

}
