# compound-calculator
Only result of all inputs







using Microsoft.VisualBasic;
using System.Windows.Forms;
class InputDialog {
    static void Main() {
        double startSum, yearPercents, yearCounts, addMoney;
        string enterSumm, yearPercentIncome, years, addedMoney;

        enterSumm = Interaction.InputBox("Введите стартовую сумму");
        yearPercentIncome = Interaction.InputBox("Введите проценты годовых");
        years = Interaction.InputBox("Введите кол-во лет");
        addedMoney = Interaction.InputBox("Сумма пополнений");

        addMoney = double.Parse(addedMoney);
        startSum = double.Parse(enterSumm);
        yearPercents = double.Parse(yearPercentIncome);
        yearCounts = double.Parse(years);
        
        if (addMoney <= 0)
        {
            double moneyPerYear = startSum + (startSum * (yearPercents * 0.01));
            for (int i = 1; i < yearCounts; i++)
            {
                moneyPerYear = moneyPerYear + (moneyPerYear * (yearPercents * 0.01));
            }
            System.Console.WriteLine(moneyPerYear);
            System.Console.ReadKey();
        }
        else
        {
            double moneyPerYear = startSum + addMoney + ((startSum+addMoney) * (yearPercents * 0.01));
            for (int i = 1; i < yearCounts; i++)
            {
                moneyPerYear = moneyPerYear + addMoney + ((moneyPerYear+addMoney) * (yearPercents * 0.01));
            }
            System.Console.WriteLine(moneyPerYear);
            System.Console.ReadKey();
        }
        
    }
}
