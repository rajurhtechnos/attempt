# attempt
Attempt and Testing
hii i am raju new to github 



try{
	URL myURL = new URL("https://fcm.googleapis.com/fcm/send");
    HttpURLConnection myURLConnection = (HttpURLConnection)myURL.openConnection();
   
   
   
    myURLConnection.setRequestProperty ("Authorization", "key=YOURKEYY");
    myURLConnection.setRequestMethod("POST");
    myURLConnection.setRequestProperty("Content-Type", "application/json");
   // myURLConnection.setRequestProperty("Content-Length", "" + postData.getBytes().length);
    myURLConnection.setRequestProperty("Content-Language", "en-US");
    myURLConnection.setUseCaches(false);
    myURLConnection.setDoInput(true);
    myURLConnection.setDoOutput(true);
    myURLConnection.connect();
  //  System.out.println("Connected!");


			    JSONObject json = new JSONObject();
               // System.out.println("these are going to "+HS);
			    json.put("registration_ids", HS);  // device token Set 
			    JSONObject info = new JSONObject();
			    info.put("title", title);  // Notification title
			    info.put("body", message);  // Notification
			    info.put("click_action", "NotificationsActivity");
			    json.put("notification", info);
			  
			        OutputStreamWriter wr = new OutputStreamWriter(
			        		myURLConnection.getOutputStream());
			        wr.write(json.toString());
			        wr.flush();
			        
			       

					BufferedReader br = new BufferedReader(new InputStreamReader((myURLConnection.getInputStream())));

					String output;
					System.out.println("Output from Server .... \n");
					while ((output = br.readLine()) != null) {
						System.out.println(output);

					}
	}
	catch(Exception ex)
	{
		ex.printStackTrace();
	}
