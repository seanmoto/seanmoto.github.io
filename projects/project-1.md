---
layout: project
type: project
image: images/mapleglobalsq.jpg
title: MapleGlobal
permalink: projects/mapleglobal
# All dates must be YYYY-MM-DD format!
date: 2017-08-23
labels:
  - Game Development
  - Javascript
  - C#
summary: A fanmade project for recreating the beginning versions of the game MapleStory.
---

<img class="ui image" src="{{ site.baseurl }}/images/mgbanner.jpg">

Released at the end of August 2017, MapleGlobal is a fanmade recreation of the first 39 versions of the original MapleStory. The modern version of MapleStory has long outgrown its original roots, but the demand and nostalgia for the early versions of many people's childhoods remain. MapleGlobal is a fanmade project created to allow many players a chance to relive their favorite verison of the game that released nearly 13 years ago, and hundreds of players have come together to experience and create a community within the game's starting point.

<img class="ui image" src="{{ site.baseurl }}/images/npctalk.png">

For this project, I volunteered to work alongside others who have had a dream of playing the old verison of the game we all loved. My job is to script the non-player characters in the game, so I learned to write code for the many non-player character interactions the players encounter during their adventure in Javascript and later in C# when we reworked our source code. I've learned to work with the languages C# and Javascript, as well as the repository Assembla.

Here is some code that illustrates how NPCs are ran:

```c#
public void Run(IHost mHost, Character character, byte State, byte Answer, string StringAnswer, int IntegerAnswer) 
	{
	    string ThirdJob = character.Quests.GetQuestData(17070);
		
	    if (State == 0)
	    {
		PrevDialogue = 0;
		QuestDialogue = -1;
		string BasicText = "Can I help you?";
		string AvailableQuests = "";
		string InProgressQuests = "";
		string ToBeCompletedQuests = "";
		string ETC = "";
			
		if (character.PrimaryStats.Level >= 70)
		{
		   if (character.PrimaryStats.Job == 110 || character.PrimaryStats.Job == 120 || character.PrimaryStats.Job == 130)
		   {
			ETC += "\r\n#L0##bI want to make the 3rd job advancment#k#l";
		   }
		}
					
		if (!(AvailableQuests.Length == 0))
		{
		   AvailableQuests = "\r\n\r\n#r#eQUEST AVAILABLE#k#n#l" + AvailableQuests;
		}
		
		if (!(InProgressQuests.Length == 0))
		{
		   InProgressQuests = "\r\n\r\n#r#eQUEST IN PROGRESS#k#n#l" + InProgressQuests;
		}
			
		if (!(ToBeCompletedQuests.Length == 0))
		{
		   ToBeCompletedQuests = "\r\n\r\n#r#eQUEST THAT CAN BE COMPLETED#k#n#l" + ToBeCompletedQuests;
		}
	
		if (AvailableQuests.Length == 0 && InProgressQuests.Length == 0 && ToBeCompletedQuests.Length == 0 && ETC.Length == 0)
		{
		   mHost.SendOK(BasicText);
		   mHost.Stop();
		}
		else
		{
		   mHost.AskMenu(BasicText + ToBeCompletedQuests + "\r\n" + InProgressQuests + "\r\n" + AvailableQuests + "\r\n" + ETC);
		}
	}
...

}
```

The fanmade project MapleGlobal discontinued during January of 2018. We had upwards of 400 players online concurrently during our peak hours. It was a great experience learning and working together with other developers with the passion of recreating a fanmade version of Maplestory.



