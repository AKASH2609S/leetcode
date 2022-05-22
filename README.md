class Solution {
public:
    int findFinalValue(vector<int>& nums, int original) {
        sort(nums.begin(),nums.end());
        int low=0;
        int high=nums.size()-1;
        int middle;
        while(low<=high){
            int mid=low+(high-low)/2;
            if (nums[mid]==original){
                original=2*original;
                low=0;
                high=nums.size()-1;
            }
            else if(nums[mid]<original){
                low=mid+1;
            }
            else if(nums[mid]>original){
                high=mid-1;
            }
        }
        return original;
        
    }
};
