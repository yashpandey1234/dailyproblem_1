3151. Special Array I
class{
public:
    bool isArraySpecial(vector<int>& nums) {
        if(nums.size()<2)return true;
        for(int i=0;i<=nums.size()-2;i++){
        if(nums[i]&1==nums[i+1]&1){
            return false;
        }
        }
        return true;
    }
};

1752. Check if Array Is Sorted and Rotated
      class Solution {
public:
    bool check(vector<int>& nums) {
        int peak=0;
        for(int i=0;i<nums.size();i++){
            if(nums[i]>nums[(i+1)%nums.size()]){
                peak++;
            }
        }
            if(peak<=1){
                return true;
            }
            else{
                return false;
            }
        
    
    }
};
1800. Maximum Ascending Subarray Sum
class Solution {
public:
    int maxAscendingSum(vector<int>& nums) {
        int n=nums.size();
        int sum=nums[0];
        int maxsum=0;
        for(int i= 1;i<n;i++){
            if(nums[i]>nums[i-1]){
                sum+=nums[i];
            }
            else{
                maxsum=max(sum,maxsum);
                sum=nums[i];
            }
        }
        // return maxsum;
        return max(sum,maxsum);
    }

};

3105. Longest Strictly Increasing or Strictly Decreasing Subarray
      class Solution {
public:
    int longestMonotonicSubarray(vector<int>& nums) {
        int n=nums.size();
        int result=1;
        int inc=1;int dec=1;
        for(int i=1;i<n;i++){
            if(nums[i]>nums[i-1]){
                inc++;
                dec=1;
                result=max(result,inc);
            }
            else if(nums[i]<nums[i-1]){
                dec++;
                inc=1;
                result=max(result,dec);
            }else{
                inc=1;
                dec=1;
            }
        }
        return result;
    }
};


1790. Check if One String Swap Can Make Strings Equal
      class Solution {
public:
    bool areAlmostEqual(string s1, string s2) {
        map<int,pair<char,char>>charmap;
        vector<int>intdiff;
        for(int i=0;i<s1.length();i++){
            charmap[i]={s1[i],s2[i]};
            if(s1[i]!=s2[i]){
                intdiff.push_back(i);
            }
        
        }
        if(intdiff.size()==0){
            return true;
        }
        if(intdiff.size()==2){
            int i=intdiff[0];
            int j=intdiff[1];
            swap(s1[i],s2[j]);
             if(s1[i] == s2[j] && s1[j] == s2[i]){
                return true;
            
             }  
        }
        return false;
    }
};
2364. Count Number of Bad Pairs








