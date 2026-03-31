# Simple-Yield-Farming-Pool
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract SimpleYieldFarm {
    mapping(address => uint256) public staked;
    uint256 public totalStaked;
    uint256 public rewardPerToken;
    mapping(address => uint256) public userRewardPerTokenPaid;
    mapping(address => uint256) public rewards;

    function stake(uint256 amount) public {
        // Update rewards logic (simplified)
        staked[msg.sender] += amount;
        totalStaked += amount;
    }

    function claimReward() public {
        // Calculate and transfer rewards (add token logic in production)
        uint256 reward = rewards[msg.sender];
        rewards[msg.sender] = 0;
        // payable(msg.sender).transfer(reward); or token.transfer
    }
}
