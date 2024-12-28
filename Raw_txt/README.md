擋頭
BEGIN:VCALENDAR
PRODID:-//Rainlendar/iCalendarPlugin V1.6//EN
VERSION:2.0
METHOD:PUBLISH

  內容 = S1

檔尾
END:VCALENDAR


function ftab99(y,m)
{
var s,festivaly,m,i,yy,mm,d;
				
				for(d=0;d<31;d++){

				//drawCld
				if(cld[d].solarTerms == '' && cld[d].solarFestival == '' && cld[d].lunarFestival == '')
				festival = '';
				else
					festival = 
					cld[d].solarTerms + ' ' + cld[d].solarFestival + ' ' + cld[d].lunarFestival;
					
				//UID
					var yuid = "" + cld[d].sYear,muid = "" + cld[d].sMonth,duid = cld[d].sDay
					
					if(muid < 10){
					muid = "0" + muid
					}
					if(duid < 10){
					duid = "0" + duid
					} 
					
					uid = yuid + muid + duid
					
					//SUMMARY
					if(cld[d].solarTerms == ''){
					sum = (cld[d].isLeap?'閏':'') + monthName[cld[d].lMonth -1] + cDay(cld[d].lDay)
					}else{
					sum = cld[d].solarTerms
					}

			s1= 'BEGIN:VEVENT<br />UID:'+ uid +
				'<br />SUMMARY:'+ sum +
				'<br />DESCRIPTION:<br />DTSTAMP:20121224T140321Z<br />DTSTART;VALUE=DATE:'+ uid +
				'<br />TRANSP:OPAQUE<br />END:VEVENT<br />';
				
				//var tab = window.open('about:blank', '_blank');
				//tab.document.write(s1); // where 'html' is a variable containing your HTML
				//tab.document.close(); // to finish loading the page
				
				document.write(s1);
				}
	}
