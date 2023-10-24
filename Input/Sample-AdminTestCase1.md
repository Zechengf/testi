//***** TEST CASE 1 *****
USER admin
PASS admin
DPIN 4321
// test create duplicate user (460 User exists.)
REGU user1,1234
REGU user1,1234
// test upgrade FREE->FREE (310 Account type updated.)
// test upgrade, degrade (all success)
UPDA user1,FREE
UPDA user1,FREE
UPDA user1,BASIC
UPDA user1,VIP
UPDA user1,FREE
// test load movies (240 Movies loaded.)
LOAD movies.txt
// test non exist file (550 Movie file not found.)
LOAD non-exist.txt
// test wrong format movie file 
// (add one txt file to docker, not implemented yet, expected 560))
// (the correct movie format should be "name,1,1")
LOAD wrong-format.txt
// log out
LOGO
// terminate session 
QUIT