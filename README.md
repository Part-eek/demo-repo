#include<iostream>  //library me
#include<vector>
using namespace std;

int singleElement(vector<int>vec){
    int st=0;
    int end=vec.size()-1;
    if(vec.size()==1){
        return vec[0];
    }
    while(st<=end){
        int mid=st+(end-st)/2;
        if(mid==0 && vec[mid]!=vec[mid+1]){
            return vec[mid];
        }
        if(mid==vec.size()-1 && vec[mid]!=vec[mid-1]){
            return vec[mid];
        }
        if(vec[mid-1]!=vec[mid] && vec[mid+1]!=vec[mid]){
            return vec[mid];
        }

        else if(mid%2==0){
            if(vec[mid]==vec[mid-1]){
                end=mid-1;
            }
            else{ 
                st=mid+1;
            }
        }
        else{
            if(vec[mid]==vec[mid-1]){
                st=mid+1;
            }
            else{
                end=mid-1;
            }
        }
        
    }
    return -1;
}

int main(){
    
    vector<int>arr={7};
    cout<<singleElement(arr);
    

    return 0;
}
