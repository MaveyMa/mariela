// Names: Nicole Hipolito, Carlos Huizar, Mavey Ma, Mario Martinez.
// Created: Friday, Oct. 30, 2015
// Save Maria

#include <iostream>
#include <fstream>
#include <cstdlib>
#include <iomanip>
#include <cmath>
using namespace std;
//*******************************************
void printAry(double ary[], int n);
//*******************************************
double mean(double ary[], int n);
//*******************************************
double stdDev(double ary[], int n);
//*******************************************
double variance(double ary[], int numberElement);
//*******************************************
double avgMagnitude(double a[], int n);
//*******************************************
double avgPower(double a[], int n);
//*******************************************
int zeroCross(double ary[], int n);
//*******************************************
int main()
{
    ifstream fin;
    ifstream finB;
    ofstream fout;
    int count = 0;
    int count2 = 0;
    double nums, num2;
    double ary[1001];
    double ary2[1001];
    fin.open("two_a.txt");
    finB.open("two_b.txt");
    fout.open("comparison.txt");
    if(fin.fail()||fout.fail()|| finB.fail())
    {
        cout << "Error in file\n";
    }
    while(fin >> nums)
    {
        ary[count] = nums;
        count++;
    }
    while(finB >> num2)
    {
        ary2[count2] = num2;
        count2++;
    }
    double meandiff = fabs(((mean(ary, count)-mean(ary2, count2))/((mean(ary, count)+mean(ary2, count2))/2))*100);
    double stddiff = fabs(((stdDev(ary, count)-stdDev(ary2, count2))/((stdDev(ary, count)+stdDev(ary2, count2))/2))*100);
    double vardiff = fabs(((variance(ary, count)-variance(ary2, count2))/((variance(ary, count)+variance(ary2, count2))/2))*100);
    double avgPdiff = fabs(((avgPower(ary, count)-avgPower(ary2, count2))/((avgPower(ary, count)+avgPower(ary2, count2))/2))*100);
    double avgMdiff = fabs(((avgMagnitude(ary, count)-avgMagnitude(ary2, count2))/((avgMagnitude(ary, count)+avgMagnitude(ary2, count2))/2))*100);
    double zCrossdiff = abs(((double(zeroCross(ary, count))-zeroCross(ary2, count2))/((zeroCross(ary, count)+zeroCross(ary2, count2))/2))*100);
    
    fout.setf(ios::fixed);
    fout.setf(ios::showpoint);
    
    fout << "Names: Nicole Hipolito, Carlos Huizar, Mavey Ma, Mario Martinez.\n\n ";
    fout << setw(58) << "two_a.txt" << setw(31) << "two_b.txt\t" << setw(15) << "\% difference\n";
    fout.setf(ios::left);
    fout << setw(50) <<  "Mean"  << setw(30) << mean(ary, count) << setw(20) << mean(ary2, count2) << setw(20) << meandiff << endl;
    fout << setw(50) << "Standard Deviation"  << setw(30) <<  stdDev(ary, count) << setw(20) << stdDev(ary2, count2) << setw(20) << stddiff << endl;
    fout << setw(50) << "Variance"  << setw(30) <<  variance(ary, count) << setw(20) << variance(ary2, count2) << setw(20) << vardiff << endl;
    fout << setw(50) << "Average Power"  << setw(30) <<  avgPower(ary, count) << setw(20) << avgPower(ary2, count2) << setw(20) << avgPdiff << endl; 
    fout << setw(50) << "Average Magnitude"  << setw(30) << avgMagnitude(ary, count) << setw(20) << avgMagnitude(ary2, count2) << setw(20) << avgMdiff << endl;   
    fout << setw(50) << "Number fo Zero Crossings"  << setw(30) << zeroCross(ary, count) << setw(20) << zeroCross(ary2, count2) << setw(20) << zCrossdiff << endl;

/*
Which values for each data file match most closely? Standard Deviation.
Which values for each data file are most different? Number of Zero Crossings.
Are there other statistical measures that you could suggest? Get the wavelength and frequency.
Can you determine if these sound recordings are from the same person? Explain. They're not from the same person because the percent difference for number of zero crossings and average magnitude are too great.
*/
    fin.close();
    fout.close();
    finB.close();
    return 0;
}
//*******************************************
void printAry(double ary[], int n)
{
    for(int i = 0; i < n; i++)
    {
        cout << setw(7) << ary[i];
    }
    cout << endl;
}
//**********PART A: MEAN**********
double mean(double ary[], int n)
{
    double total = 0;
    double average;
    for (int ix = 0; ix < n; ix++)
    {
        total += ary[ix];
    }//END FOR LOOP
    average = total / n;
    return average;
}//END MEAN

//*******************************************
double stdDev(double ary[], int n)
{
    double var = variance(ary, n);
    return sqrt(var);
}
//*******************************************
double variance(double ary[], int numberElement)
{
    double mean1 = mean(ary, numberElement);
    double top = 0, total, x;
    for(int ix = 0; ix < numberElement; ix++)
    {
        x = pow((ary[ix] - mean1), 2);
        top += x;

    }
    total = top / numberElement;
    
    return total;
}
//*******************************************
double avgMagnitude(double a[], int n)
{
    double sum = 0, totalVal = 0;
    int i = 0;
    for(i; i < n; i++)
    {
        sum += fabs(a[i]);
    
    }
    totalVal = sum/i;
    return totalVal;
}
//*******************************************
double avgPower(double a[], int n)
{
    double sum = 0, totalVal = 0;
    int i = 0;
    for(i; i < n; i++)
    {
        sum += pow(a[i], 2);
    
    }
    totalVal = sum/i;
    return totalVal;
}
//*******************************************
int zeroCross(double ary[], int n)
{
    int count = 0;
    double previous = ary[0];
    double after;
    for(int i = 0; i < n; i++)
    {
        after = ary[i];
        if((previous > 0 && after < 0) || (previous < 0 && after > 0))
        {
            count ++;
        }
        previous = ary[i];
    }
    return count;
}
//*******************************************
