# count-sort
class Solution{
    public:
    //Function to arrange all letters of a string in lexicographical 
    //order using Counting Sort.
    string countSort(string arr){
        // code here
       
       
            int n=arr.size();
            int count[26]={0};
          for( auto ch:arr)
          {
              count[ch-'a']++;
          }
          for(int i=1;i<26;i++){
              count[i]+=count[i-1];
              
          }
          string ans(n,'_');
          for(auto ch:arr)
             {
                 ans[--count[ch-'a']]=ch;
                 
             }          
          
        
        return ans;
    }
};
