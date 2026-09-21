package org.jsp.merchant_product_app.dao;

import javax.persistence.EntityManager;
import javax.persistence.EntityManagerFactory;
import javax.persistence.EntityTransaction;
import javax.persistence.Persistence;

import org.jsp.merchant_product_app.dto.Merchant;
import org.jsp.merchant_product_app.dto.Product;

public class MerchantDao {
	
	EntityManagerFactory emf=Persistence.createEntityManagerFactory("dev");
	EntityManager em=emf.createEntityManager();
	public Merchant saveMerchant(Merchant m)
	{
		EntityTransaction etran=em.getTransaction();
		etran.begin();
		em.persist(m);
		etran.commit();
		return m;
	}	
	public Merchant updateMerchant(Merchant m)
	{
		EntityTransaction etran=em.getTransaction();
		etran.begin();
		Merchant mdb=em.find(Merchant.class,m.getId());
		if(mdb!=null)
		{
			mdb.setName(m.getName());
			mdb.setGst_num(m.getGst_num());
			mdb.setEmail(m.getEmail());
			mdb.setPhone(m.getPhone());
			mdb.setPassword(m.getPassword());
			etran.commit();
			return mdb;
		}
		else 
			return null;	
	}
	
	public Merchant findMerchantById(int id) {

	    return em.find(Merchant.class, id);
	}
	
	public Merchant findMerchantByProductId(int pid) {

	    Product pdb = em.find(Product.class, pid);

	    if (pdb != null) {
	        return pdb.getM();
	    }

	    return null;
	}
	
	public Merchant findMerchantByProductName(String pname) {

	    try {
	        return em.createQuery(
	                "select p.m from Product p where p.name=?1",
	                Merchant.class)
	                .setParameter(1, pname)
	                .getSingleResult();
	    }
	    catch (Exception e) {
	        return null;
	    }
	}
	
}
