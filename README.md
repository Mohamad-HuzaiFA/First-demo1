# First-demo1
class Solution {
public:
vector<int> searchRange(vector<int>& nums, int target) {
        int left=0,right=nums.size();
        while(left<=right)
            {
            int mid=int((left+right)/2);
            if(nums[mid]<target)
                left=mid+1;
            else if(nums[mid]>target ) 
                right=mid-1;
            else
                return [leftSide(nums,0,mid, target),rightSide(nums, mid+1,nums.size(),target)]; 
                
        }
        return [-1,-1];
    }
        int leftSide(vector<int>&nums,int left,int right,int target) {

   while(left<right)  

       {

       int mid=int((left+right)/2 );

    if(nums[mid] <target)   

       left =mid+1;

       else if(nums[mid-1]<target )

           return mid;

       else

           right=mid-1;

   }

       return left;

    } 

    int rightSide(vector <int>&nums,int left,int right,int target) {

        while(left<right) 

            {

            int mid=int((left+right)/2) ;

            if(nums[mid]>target)

                right=mid-1;

            else if(nums[mid+1]>target) 

                return mid;

            else

                left=mid+1;

        } 

        return right;

    }
};
