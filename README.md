# Array-_Project
This project is based on the basic oprations of array ,whatever i learned from basic arrays  there implementation  included in this project.

#include<bits/stdc++.h>
using namespace std;
int sumofarray(int A[],int n){
    int sum=0;
    for(int i=0;i<n;i++){
        sum=sum+A[i];
    }
    return sum;
}
int  minimumelement(int A[],int n){
    int min=A[0];
    for(int i=0;i<n;i++){
        if(A[i]<min){
            min=A[i];
        }
        
    }
    return min;
}
int  maximumelement(int A[],int n){
    int max=A[0];
    for(int i=1;i<n;i++){
        if(A[i]>max){
            max=A[i];
        }
        
    }
    return max;
}

void getelement(int A[],int e, int p){
    int po=p-1;
    if(A[po]==e){
        cout<<A[po]<<endl;
    }
    
}
int  binarysearch(int A[],int binarykey,int n){
    int l=0;
    int h=n-1;
    int mid=(l+h)/2;
    while (l<=h)
    {
        if(A[mid]==binarykey){
            return mid;
        }
        else if(A[mid]>binarykey){
            h=mid-1;
        }
        else{
            l=mid+1;
        }
    }
    return -1;
    
}
bool linearsearch(int A[],int key, int size){
    for(int i=0;i<size;i++){
        if(A[i]==key){
            return true;
        }
    }
    return false;
}

void Display(int Array[], int n){
    for (int j = 0; j < n; j++)
    {
        cout<<Array[j]<<" ";
    }
    
}
int main(){
    int n,opration;
    cout<<"Enter a size of an Array"<<endl;
    cin>>n;
    int A[n];
    cout<<"Please Enter an Array"<<endl;
    for (int i = 0; i < n; i++)
    {
        cin>>A[i];
    }
    cout<<"Which opration yo have to perform "<<endl;
    cout<<"1.Display Array"<<endl;
    cout<<endl;
    cout<<"2.Insert Element in array"<<endl;
    cout<<endl;
    cout<<"3.Delete Element from Array"<<endl;
    cout<<endl;
    cout<<"4.Search Element in array using linear"<<endl;
    cout<<endl;
    cout<<"5.Search Element in Array using Binary search"<<endl;
    cout<<endl;
    cout<<"6.Get Element of any index"<<endl;
    cout<<endl;
    cout<<"7.Replace value by another value"<<endl;
    cout<<endl;
    cout<<"8.Find Maximun Element in an Array"<<endl;
    cout<<endl;
    cout<<"9.Find minimun Element in an Array"<<endl;
    cout<<endl;
    cout<<"10.Find sum of element in an Array"<<endl;
    cin>>opration;
    //cin>>opration
    //while(opration<12){
    switch (opration)
    {
    case 1:
         Display(A,n);
        break;
    case 2:
        int pos,element;
        cout<<"Enter a element & position of an Array"<<endl;
        cin>>element>>pos;
        cout<<"Intialy array is: "<<endl;
        Display(A,n);
        cout<<endl;
        cout<<"After insertion "<<endl;
        for(int i=0;i<n;i++){
            A[i]=i+1;
        }
        for(int i=n-1;i>=pos;i--){
            A[i]=A[i-1];
        }
        n++;
        A[pos-1]=element;
        Display(A,n);
        cout<<endl;
        break;

    case 3:
        int delindex;
        cout<<"Enter index whose element you have to be delete"<<endl;
        cin>>delindex;
        cout<<"Before deleting element: "<<endl;
        Display(A,n);
        cout<<endl;
        cout<<"Afetr delete"<<endl;
        for (int i = delindex-1; i <=n; i++)
        {
            A[i]=A[i+1];
        }
        n--;
        Display(A,n);
        break;
    
        //return -1;
    case 4:
        int key;
        cout<<"Enter a number which you have to search"<<endl;
        cin>>key;
        if(linearsearch(A,key,n)==true){
            cout<<"Given keynumber is present"<<endl;
        } 
        else{
            cout<<"Given number is not present"<<endl;
        }
        break;
    case 5:
        int binarykey;
        cout<<"Enter key number which you have to search"<<endl;
        cin>>binarykey;
        Display(A,n);
        if(binarysearch(A,binarykey,n)==-1){
            cout<<"Such type of key is not present "<<endl;
        }
        else{
            cout<<"Enter number is present "<<endl;
        }
        break;
    case 6:
        int e,p;
        Display(A,n);
        cout<<endl;
        cout<<"Enter a element & and its position"<<endl;
        cin>>e>>p;
        getelement(A,e,p);
        cout<<endl;
        break;
    case 7:
        //Replace value by another value
        Display(A,n);
        cout<<endl;
        int old_value,new_value;
        cout<<"Enter old value and new value"<<endl;
        cin>>old_value>>new_value;
        replace(A,A+n,old_value,new_value);
        cout<<"New Array";
        for(int i=0;i<n;i++){
            cout<<" "<<A[i];
        }
        cout<<endl;

        
        break;

    case 8:
       // Find Maximun Element in an Array
       Display(A,n);
       cout<<endl;
       cout<<"Maximum element is: "<<maximumelement(A,n)<<endl;
       break;
    case 9:
        //find minimum element of an array
        Display(A,n);
        cout<<endl;
        cout<<endl;
        cout<<"minimum element is: "<<minimumelement(A,n) <<endl;   
        break;
    case 10:
        Display(A,n);
        cout<<endl;
        cout<<"Sum of array is: "<<sumofarray(A,n)<<endl;  
        break;  
    default:
    cout<<"Please enter valid number "<<endl;
        break;
    }
    //}
    return 0;
}
