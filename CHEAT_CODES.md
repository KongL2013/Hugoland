# Hugoland Console Cheat Codes

Open the browser's Developer Tools (F12) and go to the Console tab. Copy and paste these commands to cheat in the game!

## Basic Resource Cheats

### Add Coins
```javascript
// Add 10,000 coins
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  gameData.coins = (gameData.coins || 0) + 10000;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Added 10,000 coins! Refresh the page to see changes.');
})();
```

### Add Gems
```javascript
// Add 1,000 gems
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  gameData.gems = (gameData.gems || 0) + 1000;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Added 1,000 gems! Refresh the page to see changes.');
})();
```

### Set Unlimited Resources
```javascript
// Set coins and gems to 999,999
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  gameData.coins = 999999;
  gameData.gems = 999999;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Set unlimited resources! Refresh the page to see changes.');
})();
```

## Player Stats Cheats

### Max Health
```javascript
// Set health to 9999
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  if (!gameData.playerStats) gameData.playerStats = {};
  gameData.playerStats.hp = 9999;
  gameData.playerStats.maxHp = 9999;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Set max health to 9999! Refresh the page to see changes.');
})();
```

### Super Attack
```javascript
// Set base attack to 1000
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  if (!gameData.playerStats) gameData.playerStats = {};
  gameData.playerStats.baseAtk = 1000;
  gameData.playerStats.atk = 1000;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Set super attack! Refresh the page to see changes.');
})();
```

### Super Defense
```javascript
// Set base defense to 500
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  if (!gameData.playerStats) gameData.playerStats = {};
  gameData.playerStats.baseDef = 500;
  gameData.playerStats.def = 500;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Set super defense! Refresh the page to see changes.');
})();
```

### God Mode (All Stats)
```javascript
// Set all stats to maximum
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  if (!gameData.playerStats) gameData.playerStats = {};
  gameData.playerStats.hp = 9999;
  gameData.playerStats.maxHp = 9999;
  gameData.playerStats.baseAtk = 1000;
  gameData.playerStats.atk = 1000;
  gameData.playerStats.baseDef = 500;
  gameData.playerStats.def = 500;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('God mode activated! Refresh the page to see changes.');
})();
```

## Zone & Progression Cheats

### Skip to Zone
```javascript
// Skip to zone 50
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  gameData.zone = 50;
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Skipped to zone 50! Refresh the page to see changes.');
})();
```

### Custom Zone
```javascript
// Set custom zone (change the number)
(() => {
  const targetZone = prompt('Enter zone number:');
  if (targetZone && !isNaN(targetZone)) {
    const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
    gameData.zone = parseInt(targetZone);
    localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
    console.log(`Jumped to zone ${targetZone}! Refresh the page to see changes.`);
  }
})();
```

## Equipment Cheats

### Add Legendary Weapon
```javascript
// Add a legendary weapon
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  if (!gameData.inventory) gameData.inventory = { weapons: [], armor: [], currentWeapon: null, currentArmor: null };
  if (!gameData.inventory.weapons) gameData.inventory.weapons = [];
  
  const legendaryWeapon = {
    id: 'cheat_weapon_' + Date.now(),
    name: 'Cheater\'s Excalibur',
    rarity: 'legendary',
    baseAtk: 999,
    level: 1,
    upgradeCost: 1
  };
  
  gameData.inventory.weapons.push(legendaryWeapon);
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Added legendary weapon! Refresh the page to see changes.');
})();
```

### Add Legendary Armor
```javascript
// Add legendary armor
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  if (!gameData.inventory) gameData.inventory = { weapons: [], armor: [], currentWeapon: null, currentArmor: null };
  if (!gameData.inventory.armor) gameData.inventory.armor = [];
  
  const legendaryArmor = {
    id: 'cheat_armor_' + Date.now(),
    name: 'Cheater\'s Divine Aegis',
    rarity: 'legendary',
    baseDef: 999,
    level: 1,
    upgradeCost: 1
  };
  
  gameData.inventory.armor.push(legendaryArmor);
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Added legendary armor! Refresh the page to see changes.');
})();
```

### Fill Inventory with Legendary Items
```javascript
// Add 10 legendary weapons and 10 legendary armors
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  if (!gameData.inventory) gameData.inventory = { weapons: [], armor: [], currentWeapon: null, currentArmor: null };
  if (!gameData.inventory.weapons) gameData.inventory.weapons = [];
  if (!gameData.inventory.armor) gameData.inventory.armor = [];
  
  const weaponNames = ['Excalibur', 'Mjolnir', 'Gungnir', 'Durandal', 'Gram', 'Balmung', 'Caladbolg', 'Fragarach', 'Galatine', 'Arondight'];
  const armorNames = ['Divine Aegis', 'Eternal Plate', 'Shadowweave', 'Celestial Ward', 'Dragon Scale', 'Phoenix Mail', 'Void Armor', 'Crystal Guard', 'Titan\'s Embrace', 'Seraph\'s Protection'];
  
  weaponNames.forEach((name, i) => {
    gameData.inventory.weapons.push({
      id: 'cheat_weapon_' + Date.now() + '_' + i,
      name: name,
      rarity: 'legendary',
      baseAtk: 800 + (i * 20),
      level: 1,
      upgradeCost: 1
    });
  });
  
  armorNames.forEach((name, i) => {
    gameData.inventory.armor.push({
      id: 'cheat_armor_' + Date.now() + '_' + i,
      name: name,
      rarity: 'legendary',
      baseDef: 400 + (i * 10),
      level: 1,
      upgradeCost: 1
    });
  });
  
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('Added 10 legendary weapons and 10 legendary armors! Refresh the page to see changes.');
})();
```

## Utility Cheats

### View Current Game Data
```javascript
// Display current game state
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  console.log('Current Game Data:', gameData);
})();
```

### Reset Game
```javascript
// Reset the entire game
(() => {
  if (confirm('Are you sure you want to reset the entire game? This cannot be undone!')) {
    localStorage.removeItem('hugoland_game_state');
    console.log('Game reset! Refresh the page to start over.');
  }
})();
```

### Backup Game Data
```javascript
// Create a backup of your game data
(() => {
  const gameData = localStorage.getItem('hugoland_game_state');
  if (gameData) {
    console.log('=== GAME BACKUP ===');
    console.log('Copy this text and save it somewhere safe:');
    console.log(gameData);
    console.log('=== END BACKUP ===');
  } else {
    console.log('No game data found to backup.');
  }
})();
```

### Restore Game Data
```javascript
// Restore game data from backup
(() => {
  const backupData = prompt('Paste your backup data here:');
  if (backupData) {
    try {
      JSON.parse(backupData); // Validate JSON
      localStorage.setItem('hugoland_game_state', backupData);
      console.log('Game data restored! Refresh the page to see changes.');
    } catch (e) {
      console.error('Invalid backup data format!');
    }
  }
})();
```

## Ultimate Cheat (Everything)
```javascript
// Activate all cheats at once
(() => {
  const gameData = JSON.parse(localStorage.getItem('hugoland_game_state') || '{}');
  
  // Resources
  gameData.coins = 999999;
  gameData.gems = 999999;
  
  // Stats
  if (!gameData.playerStats) gameData.playerStats = {};
  gameData.playerStats.hp = 9999;
  gameData.playerStats.maxHp = 9999;
  gameData.playerStats.baseAtk = 1000;
  gameData.playerStats.atk = 1000;
  gameData.playerStats.baseDef = 500;
  gameData.playerStats.def = 500;
  
  // Zone
  gameData.zone = 100;
  
  // Inventory
  if (!gameData.inventory) gameData.inventory = { weapons: [], armor: [], currentWeapon: null, currentArmor: null };
  if (!gameData.inventory.weapons) gameData.inventory.weapons = [];
  if (!gameData.inventory.armor) gameData.inventory.armor = [];
  
  // Add ultimate weapon
  const ultimateWeapon = {
    id: 'ultimate_weapon',
    name: '🗡️ ULTIMATE CHEATER SWORD 🗡️',
    rarity: 'legendary',
    baseAtk: 9999,
    level: 999,
    upgradeCost: 1
  };
  
  // Add ultimate armor
  const ultimateArmor = {
    id: 'ultimate_armor',
    name: '🛡️ ULTIMATE CHEATER ARMOR 🛡️',
    rarity: 'legendary',
    baseDef: 9999,
    level: 999,
    upgradeCost: 1
  };
  
  gameData.inventory.weapons.push(ultimateWeapon);
  gameData.inventory.armor.push(ultimateArmor);
  gameData.inventory.currentWeapon = ultimateWeapon;
  gameData.inventory.currentArmor = ultimateArmor;
  
  localStorage.setItem('hugoland_game_state', JSON.stringify(gameData));
  console.log('🎉 ULTIMATE CHEAT ACTIVATED! 🎉');
  console.log('You now have unlimited resources, max stats, ultimate equipment, and are in zone 100!');
  console.log('Refresh the page to see all changes.');
})();
```

## How to Use

1. Open the game in your browser
2. Press F12 to open Developer Tools
3. Click on the "Console" tab
4. Copy and paste any of the cheat codes above
5. Press Enter to execute
6. Refresh the page to see the changes

**Note:** These cheats modify your saved game data. Make sure to backup your game first if you want to preserve your original progress!