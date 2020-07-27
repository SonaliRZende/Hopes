# Hopes
First Repository

Hi Companions,
here is my first code.
---------------------------------------------------------------------------------------------------------------------------

//Function to check wether the point lies inside the poligon or not. if yes return true else false

Class Hopes
{
  static int INFINITE=10000;
  
  static class Point 
  {
    int x;
    int y;
    
      public Point(int x, int y)
      {
        this.x=x;
        this.y=y;
      }
  };
  
    static boolean onSegment(Point p, Point q, Point r)
    {
      if(q.x<=Math.max(p.x , r.x) && q.x>=Math.max(p.x , r.x) && q.y<=Math.max(p.y , r.y) && q.y>=Math.max(p.y , r.y))
      {
         return true;
      }
      return false;
    }
    
    static boolean doIntersect(Pont p1, Point q1, Point p2, Point q2)
    {
      int o1= orientation(p1,q1,p2);
      int o2= orientation(p1,q1,p2);
      int o3= orientation(p2,q2,p1);
      int o4= orientation(p2,q2,q1);
      
      if(o1!=o2 && o3!=o4)
      {
        return true;
      }
    }
     
     static boolean isPointInside(Point polygon[], int n, Point p)
   {
    
    if(n<3)
    {
        return false;
    }
    //The Point class represents a location in a two-dimensional (x, y)
    Point p=new Pont(INFINITE, p.y);
    int count=0, i=0;
    
    do
    {
        int next=(i+1)%n;
        
        if(doIntersect(polygon[i] , polygon[next], p , extreme))
        {
            if(Orientation(polygon[i], p , polygon[next])==0)
            {
                 return onSegment(polygon[i],p,polygon[next]);
            }
            count++
        }
        i=next;
    
    }while(i!=0)
    
    //Return true if count is odd , false or otherwise.
    return (count%2==1);
 


 }
}//end of class

//Driver code
public static void main(String args[])
{
    Point polygon[]={ new Point(1,0),
                      new Point(8,3),
                      new Point(8,8),
                      new Point(1,5)
                    } 
     int n=polygon.length;
     Point p=new Point(3,5);
     if(isPontInside(polygon,n,p))
     {
           System.out.println("True");
     }
     else
     {
          System.out.println("False");
     }
}
