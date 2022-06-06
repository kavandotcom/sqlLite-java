/**
 * Get the movies whose actor has apeared more than one time
 * @param count 
 */
public void getCountGreaterThan(int count){
           String sql = "SELECT movie "
                      + "FROM movies WHERE count(actor) > 1";
    
    try (Connection conn = this.connect();
         PreparedStatement pstmt  = conn.prepareStatement(sql)){
        
        // set the value
        pstmt.setInt(1,count);
        //
        ResultSet rs  = pstmt.executeQuery();
        
        // loop through the result set
        while (rs.next()) {
            System.out.println(rs.getString("movie"));
        }
    } catch (SQLException e) {
        System.out.println(e.getMessage());
    }
}



![image](https://user-images.githubusercontent.com/67421454/172087213-256e3804-c06d-4a60-8ce1-bea89374b470.png)
