$monday = (Get-Date 0:00).AddDays(-([int](Get-date).DayOfWeek)+1)

$events = (get-eventlog -EntryType Information -LogName System -InstanceId 12,13 -After $monday)

$events = $events | sort -Property TimeGenerated

foreach($event in $events){

        if($event.EventID -eq 13){
        
            $addition = "STOPP"
            $color = "Red"
        
        }else{
        
            $addition = "START"
            $color = "Green"
        
        }
        
        $DateStr = $event.TimeGenerated.ToString("$addition | yyyy-MM-dd | HH:mm:ss | dddd")
    
        write-Host -ForegroundColor $color $datestr
}
