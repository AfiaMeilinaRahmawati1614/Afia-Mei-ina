<?php
$tanggal_lahir= strtotime("2004-05-13") ;
$newformat= date ("Y-m-d",$tanggal_lahir) ;

echo "Tanggal Lahir " . "<br>" . $newformat . "<br>" ;
if ($d=="Fri") 
echo "Have a nice weekend!"; 
else 
echo "Have a nice day!". "<br>" . "Umur anda saat ini " . "<br>" ;

function hitung_umur($tanggal_lahir){
	$birthDate = new DateTime($tanggal_lahir);
	$today = new DateTime("today");
	if ($birthDate > $today) { 
	    exit("0 tahun 0 bulan 0 hari");
	}
	$y = $today->diff($birthDate)->y;
	$m = $today->diff($birthDate)->m;
	$d = $today->diff($birthDate)->d;
	return $y." tahun ".$m." bulan ".$d." hari";
}

echo hitung_umur("2004-05-13") . "<br>" ;

function getDay($date){
 $convert=gmdate($date,time()+60*60*8);
 $pecah=explode("-",$convert);
 $tgl=$pecah[2];
 $bln=$pecah[1];
 $thn=$pecah[0];
 $day=date("l",mktime(0,0,0,$bln,$tgl,$thn));
 return $day;
}


?>
