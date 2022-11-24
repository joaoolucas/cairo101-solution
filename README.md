# Solutions to [StarkNet-Edu Cairo Course](https://github.com/starknet-edu) 🌱

## [StarkNet Cairo 101](https://github.com/starknet-edu/starknet-cairo-101)

**Simple tutorials to learn how to read Cairo contracts. It's a learn to earn, so each exercise completed give you tokens.**

## Addresses of the exercises and contracts

| Topic                                 | Contract code                                         | Contract on Voyager                                                                                              |
| ------------------------------------- | ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Points counter ERC20                  | [Points counter ERC20](contracts/token/TDERC20.cairo) | [Link](https://goerli.voyager.online/contract/0x5c6b1379f1d4c8a4f5db781a706b63a885f3f9570f7863629e99e2342ac344c) |
| General syntax                        | [Ex01](contracts/ex01.cairo)                          | [Link](https://goerli.voyager.online/contract/0x29e2801df18d7333da856467c79aa3eb305724db57f386e3456f85d66cbd58b) |
| Storage variables, getters, asserts   | [Ex02](contracts/ex02.cairo)                          | [Link](https://goerli.voyager.online/contract/0x18ef3fa8b5938a0059fa35ee6a04e314281a3e64724fe094c80e3720931f83f) |
| Reading and writing storage variables | [Ex03](contracts/ex03.cairo)                          | [Link](https://goerli.voyager.online/contract/0x79275e734d50d7122ef37bb939220a44d0b1ad5d8e92be9cdb043d85ec85e24) |
| Mappings                              | [Ex04](contracts/ex04.cairo)                          | [Link](https://goerli.voyager.online/contract/0x2cca27cae57e70721d0869327cee5cb58098af4c74c7d046ce69485cd061df1) |
| Variable visibility                   | [Ex05](contracts/ex05.cairo)                          | [Link](https://goerli.voyager.online/contract/0x399a3fdd57cad7ed2193bdbb00d84553cd449abbdfb62ccd4119eae96f827ad) |
| Functions visibility                  | [Ex06](contracts/ex06.cairo)                          | [Link](https://goerli.voyager.online/contract/0x718ece7af4fb1d9c82f78b7a356910d8c2a8d47d4ac357db27e2c34c2424582)   |
| Comparing values                      | [Ex07](contracts/ex07.cairo)                          | [Link](https://goerli.voyager.online/contract/0x3a1ad1cde69c9e7b87d70d2ea910522640063ccfb4875c3e33665f6f41d354a)  |
| Recursions level 1                    | [Ex08](contracts/ex08.cairo)                          | [Link](https://goerli.voyager.online/contract/0x15fa754c386aed6f0472674559b75358cde49db8b2aba8da31697c62001146c) |
| Recursions level 2                    | [Ex09](contracts/ex09.cairo)                          | [Link](https://goerli.voyager.online/contract/0x2b9fcc1cfcb1ddf4663c8e7ac48fc87f84c91a8c2b99414c646900bf7ef5549)  |
| Composability                         | [Ex10](contracts/ex10.cairo)                          | [Link](https://goerli.voyager.online/contract/0x8415762f4b0b0f44e42ac1d103ac93c3ea94450a15bb65b99bbcc816a9388) |
| Importing functions                   | [Ex11](contracts/ex11.cairo)                          | [Link](https://goerli.voyager.online/contract/0xab5577b9be8948d89dbdba63370a3de92e72a23c4cacaea38b3a74eec3a872) |
| Events                                | [Ex12](contracts/ex12.cairo)                          | [Link](https://goerli.voyager.online/contract/0x24d15e02ddaa19d7ecd77204d35ed9bfff00a0cabc62eb3da5ba7680e44baf9) |
| Privacy on StarkNet                   | [Ex13](contracts/ex13.cairo)                          | [Link](https://goerli.voyager.online/contract/0x2bae9190076c4252289b8a8671277cef57318192cff20c736808b0c71095895) |
| Multicall                             | [Ex14](contracts/ex14.cairo)                          | [Link](https://goerli.voyager.online/contract/0xed7ddffe1370fbbc1974ab8122d1d9bd7e3da8d829ead9177ea4249b4caef1) |

## Solutions 

### Ex01 - General syntax

Very simple task, just open the contract in Voyager, go to "Write Contract" and call the function "claim_points".

### Ex02 - Storage variables, getters, asserts

Here you need to first go in "Read Contract" and call "my_secret_value". Use the result in the function "claim_points" at "Write Contract".

### Ex03 - Reading and writing storage variables

Examinating the contract we can see that the value we need is 7. In "Write Contract" we have 4 functions, in order to get to 7 points we going have to call "increment_counter" 4 times, each one giving us 2 points. After that, we can call "decrement_counter" that will remove 1 point. We can check how many points we have at "Read Contract" in the "user_counters" function. With 7 points we can call the function "claim_points".

### Ex04 - Mappings

First let's get a slot, call the function "assign_user_slot" at "Write Contract" to do that. Now at "Read Contract" you can check your slot and the value mapped to that slot with the functions "user_slots" and "values_mapped", respectively.

To claim the points of this task we have to give to the function the "expected_value". Looking at the contract we see that the expected value is the value mapped minus 32. So just make the calculation and input the answer in "claim_points" to complete this exercise.

### Ex05 - Variable visibility

Similar to Ex04, we need to call the function "assign_user_slot" at "Write Contract" and then call "copy_secret_value_to_readable_mapping". Then verify the value at "Read Contract" calling the "user_values" function. Then just put the output of "user_values" in "claim_points" at "Write Contract".

### Ex06 - Functions visibility

Similar to the previous, call "assign_user_slot" and then call "external_handler_for_internal_function" that takes "0" as input (we know that the "0" is the correct input by looking at the contract code). Now go to "Read Contract" and check the correct value calling "user_values", then just put the result in "claim_points".

### Ex07 - Comparing values

For this exercise, we basically just need to look at the code of the contract. To call "claim_points" we need two values, "a_value" and "b_value". Checking the contract, we see that "a_value" has to bee a number different from 0, less than 75 and between 40 and 69. The "b_value" cannot be negative and must be less than 1. For example, a correct input would be 50 for "a_value" and 0 for "b_value".

### Ex08 - Recursions level 1

Here we're going to need to input an array at "set_user_values". Looking at the contract we find out that the array consists in a recursive function, and to call "claim_points" we need to the user_value as 10 in the slot 10. The code maps the variables recursively to set all the user_values, so at the end of the array it's start summing. In practice the values are stored in the slots every time the function is called and continuously from 0. So to make the user_value be 10 in slot 10, we will make the following input in "set_user_values": 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10

If you want to check it, call the function "user_values" in "Read Contract". Now just call "claim_points" to finish this exercise.

### Ex09 - Recursions level 2

Looking at the contract we can see that to call the function "claim_points" we need to input a array that have at least length 4 and the sum of the numbers is greater than 50. Also, the value at index i should be at least the sum of values of index strictly higher than i. A valid input would be, for example: 30, 20, 1, 1 

In "Read Contract" you can call "get_sum" to test arrays. After you checked, just go to "claim_points" and input your answer in "array".

### Ex10 - Composability

This exercise uses composability, so we're going to have to explore two contracts to solve this. We can find the address of the second contract calling the function "ex10b_address" in "Read Contract" (remember that addresses are used in hex). Now open the second contract in Voyager and go to "Read Contract", there you will find the function "secret_value". The output of this function it's the correct input for "claim_points" in the first contract. You can choose the other value, but looking at the contract we know that this value can't be 0. 

### Ex11 - Importing functions

Here we can see by the contract the a lot of funcions are imported from another contract. We can find this contract in the "utils" folder at this course repository or just open this [link](https://github.com/starknet-edu/starknet-cairo-101/blob/main/contracts/utils/ex11_base.cairo). In this contract we can see that the secret_value outputed by the "secret_value" function in "Read Contract" of the main contract actually it's added with 42069. So call the function, subtract the result by 42069 and input the result in "claim_points". You can choose the second value.

### Ex12 - Events

As the name sugests, here we're going to just look at the event to claim the points. First let's get a slot calling the function "assign_user_slot" in "Write Contract". Then, head to "Write Contract" and put anything at "claim_points", just to trigger the event and open the error message. There you will find the correct expected_value.

### Ex13 - Privacy on StarkNet

This exercise can be solved the same way that Ex12. Not sure if this should be this way since the comments in the contract indicate other resolution.

### Ex14 - Multicall

Check the contract at /contracts 
Deployed contract: https://goerli.voyager.online/contract/0x02c67f7a911a90c7ccab6a264f9d61cb7567e8f9a3838362f340e6f5599b579e
