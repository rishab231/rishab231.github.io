---
layout: post
title: Project FUT
subtitle: A handy tool to build your best FIFA ultimate team
---

### Overview
This application helps you build the best FIFA ultimate team possible with a given set of resources. This project is has been designed using two fundamental APIs:

Author: Rishab Srivastava

**A. Graph API** 
This API uses an algorithm based on a graph's neighbours functionality to calculate the chemistry for a given ultimate team with a certain formation. 

<!--![Chemistry](http://guides.gamepressure.com/fifa17/gfx/word/95831741.jpg) -->
<img src = "http://guides.gamepressure.com/fifa17/gfx/word/95831741.jpg" width="425">
<img src = "https://lh3.googleusercontent.com/8I7P-XGi6yY0xRtum-owHzVUvmRrYVpWDINNHPK3L7XuPtBK86sRf0CAQsGYx0YMZ08=w300" width="225">

```java
public class GraphFUT {
	private Database db;
	private int numcoins;
	private Map<Integer, Position> positions;
	private Formation teamf; //The desired formation of the team
	public GraphFUT(Database db, Integer c, Formation f);
	//Returns true if two players are connected
	boolean isConnected(int x, int y);
	//Returns 0 if red line, 1 for orange line and 2 for green line
	int chemistry(int x, int y);
	/* Prints the best possible team with the given number of coins
	and the given set of players in the database */
	void bestTeam();
}
```

**B. Data Science API** 
Instead of using a built-in data science/machine learning library or framework such as Pandas or Java-ML, I decided to build my own DS-API with custom functionality and feature set. 

Details for both APIs to follow.

## FUT Data
Our program will include a readable csv file which will contain data about each player available in FIFA Ultimate team. Each record will contain details about the player such as Name, Nation, Club, Beast Rating, and Average Price of the player's card.

This CSV file will be parsed using the Data Science API and fed into the Graph API to maximize the chemistry of the team. Hence, a team will be formed contingent to the user's available resources (Coins, Points) as well as his preferences (League/Nation).

*Additional: 
A UI which further takes into account the user's playing style can also be created. For example, a user might prefer pace in their attackers over finishing ability or heading ability in their defenders over defending.*

### Commands

### Definitions

---

### FAQ
**Q1. What is FIFA Ultimate team?**
 FIFA Ultimate Team (commonly called FUT) is a mode in FIFA. It enables you build teams using any players from all the leagues to play offline and online to win coins to buy better players or packs which contain random players.
 
### Update Log

### Citations

*Data*

*Images*

1. http://guides.gamepressure.com/fifa17/gfx/word/95831741.jpg
2. https://lh3.googleusercontent.com/

---