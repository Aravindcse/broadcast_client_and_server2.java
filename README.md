# broadcast_client_and_server2.java
//for server
import java.net.*; 
import java.io.*; 
import java.util.*; 
public class BroadcastServer
{ 
public static final int PORT = 1200; 
public static void main(String args[]) throws Exception
{ 
MulticastSocket socket; 
DatagramPacket packet; 
InetAddress address = InetAddress.getByName(); 
socket = new MulticastSocket(); 
// join a Multicast group and send the group salutations 
socket.joinGroup(address); 
byte[] data = null; 
for(;;)
{ 
 Thread.sleep(1000); 
 System.out.println("Sending "); 
 String str = (new Date()).toString(); 
 data = str.getBytes(); 
 packet = new DatagramPacket (data,str.length(),address,PORT);
 // Sends the packet 
socket.send(packet); 
 } 
 // for 
 } 
 // main 
 } // class BroadcastServer
