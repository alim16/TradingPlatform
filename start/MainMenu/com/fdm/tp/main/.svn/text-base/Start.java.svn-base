package com.fdm.tp.main;

import java.util.HashMap;
import java.util.Scanner;

import javax.naming.ldap.ControlFactory;

import com.fdm.tp.controller.ControllerFactory;
import com.fdm.tp.controller.IController;
import com.fdm.tp.controller.RegistrationController;
import com.fdm.tp.model.storable.User;
import com.fdm.tp.model.storage.MapUserStorageSingleton;
import com.fdm.tp.util.Action_RegisterUser;
import com.fdm.tp.validate.LoginValidator;
import com.fdm.tp.validate.RegistrationValidator;
import com.fdm.tp.view.View;

import org.apache.log4j.*;


public class Start {
	 
	
	 static Logger log = Logger.getLogger(Start.class.getName());
	
	public static void main(String[] args) {
		MapUserStorageSingleton.getInstance().setMap(new HashMap<String, User>());
	
		IController con = new RegistrationController(new View(new Scanner(System.in)), new RegistrationValidator(), new Action_RegisterUser(MapUserStorageSingleton.getInstance()));
		
		while(true){
			con = ControllerFactory.create(con.handle());
		}
	}

}
