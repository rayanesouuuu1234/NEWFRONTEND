<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Leaderboard</title>
</head>
<body>

<h2>Leaderboard</h2>

<table id="leaderboard">
  <thead>
    <tr>
      <th>Rank</th>
      <th>Name</th>
      <th>Score</th>
    </tr>
  </thead>
  <tbody>
    <!-- Data will be inserted here -->
  </tbody>
</table>

<script>
// Fetch leaderboard data from an external website
fetch('https://example.com/leaderboard')
  .then(response => response.json())
  .then(data => {
    const leaderboardTable = document.getElementById('leaderboard');

    data.forEach((entry, index) => {
      const row = leaderboardTable.insertRow();
      const rankCell = row.insertCell(0);
      const nameCell = row.insertCell(1);
      const scoreCell = row.insertCell(2);

      rankCell.textContent = index + 1;
      nameCell.textContent = entry.name;
      scoreCell.textContent = entry.score;
    });
  })
  .catch(error => {
    console.error('Error fetching leaderboard:', error);
  });
</script>

</body>
</html>
