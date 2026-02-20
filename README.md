//Selection

package program3;

import java.sql.*;

public class SelectDemo {
    static void main() {

        String insert_sql = "select * from student";
        try(
                Connection conn= DriverManager.getConnection("jdbc:mariadb://localhost:3307/exambase","root","root");
                PreparedStatement pst=conn.prepareStatement(insert_sql);
                ResultSet rs=pst.executeQuery();


                ) {

            while(rs.next()){
                System.out.println(rs.getInt("ID")+" "+rs.getString("NAME")+" "+rs.getString("ADDRESS"));
            }



        }catch (SQLException e){
            e.printStackTrace();
        }


    }
}
