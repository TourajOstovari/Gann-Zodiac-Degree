//+------------------------------------------------------------------+
//|                                                   gannDegree.mq4 |
//|                                  Copyright 2024, MetaQuotes Ltd. |
//|                                             https://www.mql5.com |
//+------------------------------------------------------------------+
#property copyright "Developed by Mr. Touraj Ostovari. Iran, Tabriz 2024"
#property link      "Toraj.ostovari@gmail.com"
#property version   "1.00"
#property strict
#property indicator_chart_window
//--- input parameters
input int digits = 3;
input float    PlanetDegree=0.0;
input int      Step=10;
input double   Price=1.1101;
input datetime Time_;
extern color mCol1 = Red;
extern color mCol2 = Blue;
//+------------------------------------------------------------------+
//| Custom indicator initialization function                         |
//+------------------------------------------------------------------+
int OnInit()
  {
//--- indicator buffers mapping
   
//---
   return(INIT_SUCCEEDED);
  }
   bool HLine1(const long            chart_ID=0,        // chart's ID
                 const string          name="L1",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrRed,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click


bool HLine2(const long            chart_ID=11,        // chart's ID
                 const string          name="L2",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrRed,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click
                 
  bool HLine3(const long            chart_ID=22,        // chart's ID
                 const string          name="L3",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrRed,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click               
                 
                 
 bool HLine4(const long            chart_ID=33,        // chart's ID
                 const string          name="L4",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrRed,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click                
                 
                 
                 
  bool HLine1_(const long            chart_ID=10,        // chart's ID
                 const string          name="L1_",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrBlue,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click

bool HLine2_(const long            chart_ID=20,        // chart's ID
                 const string          name="L2_",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrBlue,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click


bool HLine3_(const long            chart_ID=30,        // chart's ID
                 const string          name="L3_",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrBlue,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click

bool HLine4_(const long            chart_ID=40,        // chart's ID
                 const string          name="L4_",      // line name
                 const int             sub_window=0,      // subwindow index
                 double                price=0,           // line price
                 const color           clr=clrBlue,        // line color
                 const ENUM_LINE_STYLE style=STYLE_SOLID, // line style
                 const int             width=1,           // line width
                 const bool            back=false,        // in the background
                 const bool            selection=true,    // highlight to move
                 const bool            hidden=true,       // hidden in the object list
                 const long            z_order=0);         // priority for mouse click               
       
       
       
       
  double String1Price;
  double String2Price;
  double String3Price;
  double String4Price;
  
  double String1Price_;
  double String2Price_;
  double String3Price_;
  double String4Price_;
       
       
       
       
       
       
                 
                     
int OnCalculate(const int rates_total,
                const int prev_calculated,
                const datetime &time[],
                const double &open[],
                const double &high[],
                const double &low[],
                const double &close[],
                const long &tick_volume[],
                const long &volume[],
                const int &spread[])
  {
//---

ObjectsDeleteAll();
string str_Price = DoubleToStr(Price,digits);
string result[];
  StringSplit(str_Price,'.',result);
double PR = StrToDouble(result[1]);
while( PR >360)
  {
   PR = PR - 360;
  }
  PR = PR - PlanetDegree;
  double L1,L2,L3,L4;
  L1 = PR + Step; L2 = L1 + Step; L3 = L2 + Step; L4 = L3 + Step;
  double L1_,L2_,L3_,L4_;
  L1_ = PR - Step; L2_ = L1_ - Step; L3_ = L2_ - Step; L4_ = L3_ - Step;
  double temp_num = 0;
  if(digits == 1) temp_num = Price * 10;
  if(digits == 2) temp_num = Price * 100;
  if(digits == 3) temp_num = Price * 1000;
  if(digits == 4) temp_num = Price * 10000;
  if(digits == 5) temp_num = Price * 100000;
  if(digits == 6) temp_num = Price * 1000000;
  if(digits == 7) temp_num = Price * 10000000;
  
   String1Price = temp_num + Step;
   String2Price = String1Price + Step;
   String3Price = String2Price + Step;
   String4Price = String3Price + Step;
  
   String1Price_ = temp_num - Step ;
   String2Price_ = String1Price_ - Step;
   String3Price_ = String2Price_ - Step;
   String4Price_ = String3Price_ - Step;
  if(digits == 1) 
  {
  String1Price = String1Price / 10;
  String2Price = String2Price / 10;
  String3Price = String3Price / 10;
  String4Price = String4Price / 10;
  
  String1Price_ = String1Price_ / 10;
  String2Price_ = String2Price_ / 10;
  String3Price_ = String3Price_ / 10;
  String4Price_ = String4Price_ / 10;
  }
  if(digits == 2)
  {
  String1Price = String1Price/100;
  String2Price = String2Price / 100;
  String3Price = String3Price / 100;
  String4Price = String4Price / 100;
  
  String1Price_ = String1Price_ /100;
  String2Price_ = String2Price_ / 100;
  String3Price_ = String3Price_ / 100;
  String4Price_ = String4Price_ / 100;
  }
   
  if(digits == 3)
  {
  String1Price = String1Price / 1000;
  String2Price = String2Price / 1000;
  String3Price = String3Price / 1000;
  String4Price = String4Price / 1000;
  
    String1Price_ = String1Price_ / 1000;
  String2Price_ = String2Price_ / 1000;
  String3Price_ = String3Price_ / 1000;
  String4Price_ = String4Price_ / 1000;
  }
   
  if(digits == 4)
  {
  String1Price = String1Price / 10000;
  String2Price = String2Price / 10000;
  String3Price = String3Price / 10000;
  String4Price = String4Price / 10000;
  
    String1Price_ = String1Price_ / 10000;
  String2Price_ = String2Price_ / 10000;
  String3Price_ = String3Price_ / 10000;
  String4Price_ = String4Price_ / 10000;
  }
  if(digits == 5) 
  {
  String1Price = String1Price / 100000;
  String2Price = String2Price / 100000;
  String3Price = String3Price / 100000;
  String4Price = String4Price / 100000;
  
    String1Price_ = String1Price_ / 100000;
  String2Price_ = String2Price_ / 100000;
  String3Price_ = String3Price_ / 100000;
  String4Price_ = String4Price_ / 100000;
  }
  if(digits == 6) 
  {
  String1Price = String1Price / 1000000;
  String2Price = String2Price / 1000000;
  String3Price = String3Price / 1000000;
  String4Price = String4Price / 1000000;
  
    String1Price_ = String1Price_ / 1000000;
  String2Price_ = String2Price_ / 1000000;
  String3Price_ = String3Price_ / 1000000;
  String4Price_ = String4Price_ / 1000000;
  }
  if(digits == 7) 
  {
  String1Price = String1Price / 10000000;
  String2Price = String2Price / 10000000;
  String3Price = String3Price / 10000000;
  String4Price = String4Price / 10000000;
  
    String1Price_ = String1Price_ / 10000000;
  String2Price_ = String2Price_ / 10000000;
  String3Price_ = String3Price_ / 10000000;
  String4Price_ = String4Price_ / 10000000;
  }

  ObjectCreate("HLine1",OBJ_HLINE,0,Time_, String1Price);
  ObjectSetText("HLine1", "Degree: " + L1, Digits);
  
   ObjectCreate("HLine2",OBJ_HLINE,0,Time_, String2Price);
  ObjectSetText("HLine2", "Degree: " + L2, Digits);
  
   ObjectCreate("HLine3",OBJ_HLINE,0,Time_, String3Price);
  ObjectSetText("HLine3", "Degree: " + L3, Digits);
  
   ObjectCreate("HLine4",OBJ_HLINE,0,Time_, String4Price);
  ObjectSetText("HLine4", "Degree: " + L4, Digits);
  
  /////////////////////////////////////////////////
  
    ObjectCreate("L1_",OBJ_HLINE,0,Time_, String1Price_);
  ObjectSetText("L1_", "Degree: " + L1_, Digits);
  
   ObjectCreate("L2_",OBJ_HLINE,0,Time_, String2Price_);
  ObjectSetText("L2_", "Degree: " + L2_, Digits);
  
   ObjectCreate("L3_",OBJ_HLINE,0,Time_, String3Price_);
  ObjectSetText("L3_", "Degree: " + L3_, Digits);
  
   ObjectCreate("L4_",OBJ_HLINE,0,Time_, String4Price_);
  ObjectSetText("L4_", "Degree: " + L4_, Digits);
  
ObjectSet("HLine1", OBJPROP_COLOR, mCol1);
ObjectSet("HLine2", OBJPROP_COLOR, mCol1);
ObjectSet("HLine3", OBJPROP_COLOR, mCol1);
ObjectSet("HLine4", OBJPROP_COLOR, mCol1);

ObjectSet("L1_", OBJPROP_COLOR, mCol2);
ObjectSet("L2_", OBJPROP_COLOR, mCol2);
ObjectSet("L3_", OBJPROP_COLOR, mCol2);
ObjectSet("L4_", OBJPROP_COLOR, mCol2);














//Alert("String1Price");
//--- return value of prev_calculated for next call
   return(rates_total);
  }

void OnTimer()
  {

  string str_Price = DoubleToStr(Price,digits);
string result[];
  StringSplit(str_Price,'.',result);
double PR = StrToDouble(result[1]);
while( PR >360)
  {
   PR = PR - 360;
  }
  PR = PR - PlanetDegree;
  double L1,L2,L3,L4;
  L1 = PR + Step; L2 = L1 + Step; L3 = L2 + Step; L4 = L3 + Step;
  double L1_,L2_,L3_,L4_;
  L1_ = PR - Step; L2_ = L1_ - Step; L3_ = L2_ - Step; L4_ = L3_ - Step;
  double temp_num = 0;
  if(digits == 1) temp_num = Price * 10;
  if(digits == 2) temp_num = Price * 100;
  if(digits == 3) temp_num = Price * 1000;
  if(digits == 4) temp_num = Price * 10000;
  if(digits == 5) temp_num = Price * 100000;
  if(digits == 6) temp_num = Price * 1000000;
  if(digits == 7) temp_num = Price * 10000000;
  
   String1Price = temp_num + Step;
   String2Price = String1Price + Step;
   String3Price = String2Price + Step;
   String4Price = String3Price + Step;
  
   String1Price_ = temp_num - Step ;
   String2Price_ = String1Price_ - Step;
   String3Price_ = String2Price_ - Step;
   String4Price_ = String3Price_ - Step;
  if(digits == 1) 
  {
  String1Price = String1Price / 10;
  String2Price = String2Price / 10;
  String3Price = String3Price / 10;
  String4Price = String4Price / 10;
  
  String1Price_ = String1Price_ / 10;
  String2Price_ = String2Price_ / 10;
  String3Price_ = String3Price_ / 10;
  String4Price_ = String4Price_ / 10;
  }
  if(digits == 2)
  {
  String1Price = String1Price/100;
  String2Price = String2Price / 100;
  String3Price = String3Price / 100;
  String4Price = String4Price / 100;
  
  String1Price_ = String1Price_ /100;
  String2Price_ = String2Price_ / 100;
  String3Price_ = String3Price_ / 100;
  String4Price_ = String4Price_ / 100;
  }
   
  if(digits == 3)
  {
  String1Price = String1Price / 1000;
  String2Price = String2Price / 1000;
  String3Price = String3Price / 1000;
  String4Price = String4Price / 1000;
  
    String1Price_ = String1Price_ / 1000;
  String2Price_ = String2Price_ / 1000;
  String3Price_ = String3Price_ / 1000;
  String4Price_ = String4Price_ / 1000;
  }
   
  if(digits == 4)
  {
  String1Price = String1Price / 10000;
  String2Price = String2Price / 10000;
  String3Price = String3Price / 10000;
  String4Price = String4Price / 10000;
  
    String1Price_ = String1Price_ / 10000;
  String2Price_ = String2Price_ / 10000;
  String3Price_ = String3Price_ / 10000;
  String4Price_ = String4Price_ / 10000;
  }
  if(digits == 5) 
  {
  String1Price = String1Price / 100000;
  String2Price = String2Price / 100000;
  String3Price = String3Price / 100000;
  String4Price = String4Price / 100000;
  
    String1Price_ = String1Price_ / 100000;
  String2Price_ = String2Price_ / 100000;
  String3Price_ = String3Price_ / 100000;
  String4Price_ = String4Price_ / 100000;
  }
  if(digits == 6) 
  {
  String1Price = String1Price / 1000000;
  String2Price = String2Price / 1000000;
  String3Price = String3Price / 1000000;
  String4Price = String4Price / 1000000;
  
    String1Price_ = String1Price_ / 1000000;
  String2Price_ = String2Price_ / 1000000;
  String3Price_ = String3Price_ / 1000000;
  String4Price_ = String4Price_ / 1000000;
  }
  if(digits == 7) 
  {
  String1Price = String1Price / 10000000;
  String2Price = String2Price / 10000000;
  String3Price = String3Price / 10000000;
  String4Price = String4Price / 10000000;
  
    String1Price_ = String1Price_ / 10000000;
  String2Price_ = String2Price_ / 10000000;
  String3Price_ = String3Price_ / 10000000;
  String4Price_ = String4Price_ / 10000000;
  }
ObjectsDeleteAll();

  ObjectCreate("HLine1",OBJ_HLINE,0,Time_, String1Price);
  ObjectSetText("HLine1", "Degree: " + L1, Digits);
  
   ObjectCreate("HLine2",OBJ_HLINE,0,Time_, String2Price);
  ObjectSetText("HLine2", "Degree: " + L2, Digits);
  
   ObjectCreate("HLine3",OBJ_HLINE,0,Time_, String3Price);
  ObjectSetText("HLine3", "Degree: " + L3, Digits);
  
   ObjectCreate("HLine4",OBJ_HLINE,0,Time_, String4Price);
  ObjectSetText("HLine4", "Degree: " + L4, Digits);
  
  /////////////////////////////////////////////////
  
    ObjectCreate("L1_",OBJ_HLINE,0,Time_, String1Price_);
  ObjectSetText("L1_", "Degree: " + L1_, Digits);
  
   ObjectCreate("L2_",OBJ_HLINE,0,Time_, String2Price_);
  ObjectSetText("L2_", "Degree: " + L2_, Digits);
  
   ObjectCreate("L3_",OBJ_HLINE,0,Time_, String3Price_);
  ObjectSetText("L3_", "Degree: " + L3_, Digits);
  
   ObjectCreate("L4_",OBJ_HLINE,0,Time_, String4Price_);
  ObjectSetText("L4_", "Degree: " + L4_, Digits);
  
ObjectSet("HLine1", OBJPROP_COLOR, mCol1);
ObjectSet("HLine2", OBJPROP_COLOR, mCol1);
ObjectSet("HLine3", OBJPROP_COLOR, mCol1);
ObjectSet("HLine4", OBJPROP_COLOR, mCol1);

ObjectSet("L1_", OBJPROP_COLOR, mCol2);
ObjectSet("L2_", OBJPROP_COLOR, mCol2);
ObjectSet("L3_", OBJPROP_COLOR, mCol2);
ObjectSet("L4_", OBJPROP_COLOR, mCol2);
 /*   
  
  Print(result[1]);
  
  Alert(PR); */
  }
//+------------------------------------------------------------------+
//| ChartEvent function                                              |
//+------------------------------------------------------------------+
void OnChartEvent(const int id,
                  const long &lparam,
                  const double &dparam,
                  const string &sparam)
  {
//---
/*

    */
  }
//+------------------------------------------------------------------+
