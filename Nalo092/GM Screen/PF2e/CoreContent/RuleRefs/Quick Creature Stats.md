```dataviewjs
// Define the data as an array of objects
const data = [
    { Level: -1, Skill: 5, AC: 15, High: 8, MED: 5, Low: 2, HP: 9, Strike: "+8 for 1d4+1", Spell: "16/+8" },
    { Level: 1, Skill: 7, AC: 16, High: 10, MED: 7, Low: 4, HP: 25, Strike: "+9 for 1d6+3", Spell: "17/+9" },
    { Level: 2, Skill: 8, AC: 18, High: 11, MED: 8, Low: 5, HP: 38, Strike: "+11 for 1d10+4", Spell: "18/+10" },
    { Level: 3, Skill: 10, AC: 19, High: 12, MED: 9, Low: 6, HP: 55, Strike: "+12 for 1d10+6", Spell: "20/+12" },
    { Level: 4, Skill: 12, AC: 21, High: 14, MED: 11, Low: 8, HP: 75, Strike: "+14 for 2d8+5", Spell: "21/+13" },
    { Level: 5, Skill: 13, AC: 22, High: 15, MED: 12, Low: 9, HP: 95, Strike: "+15 for 2d8+7", Spell: "22/+14" },
    { Level: 6, Skill: 15, AC: 24, High: 17, MED: 14, Low: 11, HP: 120, Strike: "+17 for 2d8+9", Spell: "24/+16" },
    { Level: 7, Skill: 17, AC: 25, High: 18, MED: 15, Low: 12, HP: 145, Strike: "+18 for 2d10+9", Spell: "25/+17" },
    { Level: 8, Skill: 18, AC: 27, High: 19, MED: 16, Low: 13, HP: 170, Strike: "+20 for 2d10+11", Spell: "26/+18" },
    { Level: 9, Skill: 20, AC: 28, High: 21, MED: 18, Low: 15, HP: 195, Strike: "+21 for 2d10+13", Spell: "28/+20" },
    { Level: 10, Skill: 22, AC: 30, High: 22, MED: 19, Low: 16, HP: 220, Strike: "+23 for 2d12+13", Spell: "29/+21" },
    { Level: 11, Skill: 23, AC: 31, High: 24, MED: 21, Low: 18, HP: 245, Strike: "+24 for 2d12+15", Spell: "30/+22" },
    { Level: 12, Skill: 25, AC: 33, High: 25, MED: 22, Low: 19, HP: 270, Strike: "+26 for 3d10+14", Spell: "32/+24" },
    { Level: 13, Skill: 27, AC: 34, High: 26, MED: 23, Low: 20, HP: 295, Strike: "+27 for 3d10+16", Spell: "33/+25" },
    { Level: 14, Skill: 28, AC: 36, High: 28, MED: 25, Low: 22, HP: 320, Strike: "+29 for 3d10+18", Spell: "34/+26" },
    { Level: 15, Skill: 30, AC: 37, High: 29, MED: 26, Low: 23, HP: 345, Strike: "+30 for 3d12+17", Spell: "36/+28" },
    { Level: 16, Skill: 32, AC: 39, High: 30, MED: 28, Low: 25, HP: 370, Strike: "+32 for 3d12+18", Spell: "37/+29" },
    { Level: 17, Skill: 33, AC: 40, High: 32, MED: 29, Low: 26, HP: 395, Strike: "+33 for 3d12+19", Spell: "38/+30" },
    { Level: 18, Skill: 35, AC: 42, High: 33, MED: 30, Low: 27, HP: 420, Strike: "+35 for 3d12+20", Spell: "40/+32" },
    { Level: 19, Skill: 37, AC: 43, High: 35, MED: 32, Low: 29, HP: 445, Strike: "+36 for 4d10+20", Spell: "41/+33" },
    { Level: 20, Skill: 38, AC: 45, High: 36, MED: 33, Low: 30, HP: 470, Strike: "+38 for 4d10+22", Spell: "42/+34" }
];

// Function to update the display based on selected level
function updateDisplay(level) {
    const selectedData = data.find(d => d.Level === parseInt(level));
    dv.container.empty();
    dv.paragraph("Select Level:");
    dv.container.appendChild(select);

    // Create a table for displaying data
    const table = dv.container.createEl('table', { cls: 'dataview table' });
    const tbody = table.createEl('tbody');

    // Helper function to add rows to the table
    function addRow(label, value) {
        const row = tbody.createEl('tr');
        row.createEl('td', { text: label, cls: 'dataview-table-label' });
        row.createEl('td', { text: value, cls: 'dataview-table-value' });
    }

    // Add data to the table
    addRow('Ability Checks', selectedData.Skill);
    addRow('AC', selectedData.AC);
    addRow('High Save', selectedData.High);
    addRow('Medium Save', selectedData.MED);  // Updated to 'MED'
    addRow('Low Save', selectedData.Low);
    addRow('HP', selectedData.HP);
    addRow('Strike', selectedData.Strike);
    addRow('Spell DC & Attack', selectedData.Spell);
}

// Setup the level selector and initialize the display
const select = dv.container.createEl("select", { attr: { id: 'level-select' } });
data.forEach(entry => {
    const option = select.createEl("option", { text: entry.Level });
    option.value = entry.Level;
});
select.addEventListener('change', () => updateDisplay(select.value));
updateDisplay(select.value); // Initial display update
```

