Die Vertikalen und die Diagonalen Checks wurden verbessert: 
    protected override (string?, string?)? HorizontalWinner()
    {
        for (int i = 0; i < 3; i++)
        {
            if (_field[i, 0] != null && _field[i, 0] == _field[i, 1] && _field[i, 1] == _field[i, 2])
                return (_field[i, 0], "Horizontal");
        }
        return null;
    }

    protected override (string?, string?)? VerticalWinner()
    {
        for (int i = 0; i < 3; i++)
        {
            if (_field[0, i] != null && _field[0, i] == _field[1, i] && _field[1, i] == _field[2, i])
                return (_field[0, i], "Vertical");
        }
        return null;
    }

    protected override (string?, string?)? DiagonalWinner1()
    {
        return (_field[0, 0] != null && _field[0, 0] == _field[1, 1] && _field[1, 1] == _field[2, 2]) 
            ? (_field[0, 0], "Diagonal (\\)") : null;
    }

    protected override (string?, string?)? DiagonalWinner2()
    {
        return (_field[0, 2] != null && _field[0, 2] == _field[1, 1] && _field[1, 1] == _field[2, 0]) 
            ? (_field[0, 2], "Diagonal (/)") : null;
    }
}
