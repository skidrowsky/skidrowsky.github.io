usage: string columnLetter = ColumnIndexToColumnLetter(100); // returns CV
static string ColumnIndexToColumnLetter(int colIndex)
{
    int div = colIndex;
    string colLetter = String.Empty;
    int mod = 0;
 
    while (div > 0)
    {
        mod = (div - 1) % 26;
        colLetter = (char)(65 + mod) + colLetter;
        div = (int)((div - mod) / 26);
    }
    return colLetter;
}

usage: int columnIndex = ColumnLetterToColumnIndex("XFD"); // returns 16384
static int ColumnLetterToColumnIndex(string columnLetter)
{
    columnLetter = columnLetter.ToUpper();
    int sum = 0;

    for (int i = 0; i < columnLetter.Length; i++)
    {
        sum *= 26;
        sum += (columnLetter[i] - 'A' + 1);
    }
    return sum;
}
