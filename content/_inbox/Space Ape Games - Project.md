2023-11-26
Tags: #interview #project

- build a `LeaderboardClient` library
- `LeaderboardClient` integrates with a given `LeaderboardServer`
- refactor the `leaderboardUI.cs` into the `leaderboardClient.cs` (time blocked to 3 hours)
- the aim is to create a `LeaderboardClient` library that is reusable across multiple games to provide a simple API to integrate with `LeaderboardServer`
- `LeaderboardClient` should target NetStandard2.1 framework
- `LeaderboardClient` should not include any Unity dependencies

They will look at API design, code quality, and performance

Not expected to use Unity
`GamePrototype/UnityLeaderboardProject` is the Unity project used to construct the `LeaderboardUI` source

`LeaderboardClient`: an empty class for your implementation
	.NET Standard 2.1
	Class Library
`LeaderboardServer`: a provided leaderboard server to integrate
	.NET 7.0
	Console Application
`LeaderboardUI`: a tiny slice of a Unity Game UI
	.NET Standard 2.1
	Class Library



---
# References
