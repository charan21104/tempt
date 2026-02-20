//Insertion

package program3;

import java.sql.*;
import java.util.Comparator;

public class InsertDemo {
    static void main() {

        String insert_sql = "insert into student(id,name,address) values(?,?,?)";
        try(
                Connection conn= DriverManager.getConnection("jdbc:mariadb://localhost:3307/exambase","root","root");
                PreparedStatement pst=conn.prepareStatement(insert_sql);


                ) {
            pst.setInt(1,101);
            pst.setString(2,"A");
            pst.setString(3,"Hyderabad");
            pst.executeUpdate();

            pst.setInt(1,102);
            pst.setString(2,"B");
            pst.setString(3,"Chennai");
            pst.executeUpdate();

            pst.setInt(1,103);
            pst.setString(2,"C");
            pst.setString(3,"BLR");
            pst.executeUpdate();

            pst.setInt(1,104);
            pst.setString(2,"D");
            pst.setString(3,"Pune");
            pst.executeUpdate();

            pst.setInt(1,105);
            pst.setString(2,"E");
            pst.setString(3,"Hyderabad");
            pst.executeUpdate();



        }catch (SQLException e){
            e.printStackTrace();
        }


    }
}
