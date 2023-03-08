# PracticeWebSocket

The chat web includes 5 rooms : Bronze, Silver, Gold, Platinum, and Ruby. In each room, when a new member joins, there is a notification and only the new member is notified about the message history in that room.

Scenario:

Create user named Ryan, enter room Platinum and say "Hello".

![img0](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/0.png)
![img1](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/1.png)

Create another user named Liz, enter room Platinum. In this stage, Liz can view the message history from Ryan (which is "Hello"). Use Liz account to say "Hi Ryan".

![img2](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/2.png)
![img3](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/3.png)

As Ryan's view, Liz's join and new message (which is "Hi Ryan") are notified.

![img4](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/4.png)

When turning to the backend console log, first of all, the contents of the above chat are sent to Kafka and logged out by Kafka listener in format "sender: content".

![img5](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/5.png)

The implementation for the above behavior is that each message is sent to Kafka inside sendMessage function.

![img8](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/8.png)

***
Docker compose file:

![img6](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/6.png)

And 2 commands for start and stop Kafka through Docker composer is

'''
// Start docker-compose
docker-compose up -d

// End docker-compose
docker-compose down
'''

![img7](https://github.com/LHN2225/PracticeWebSocket/blob/main/result%20image/7.png)