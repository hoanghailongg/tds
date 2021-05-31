error_reporting(0); session_start(); $do="\033[1;91m"; $maufulldo= "\e[1;47;31m"; $maunenhong= "\033[1;41;33m"; $res="\033[0m"; $red="\e[1;31m"; $pink="\e[1;35m"; $green="\e[1;32m"; $yellow="\e[1;33m"; $y2="\033[0;33m"; $white= "\033[0;37m"; $cyan= "\e[1;36m"; $blue="\e[1;34m"; $ngreen="\033[42m"; $ngblack="\033[40m"; $nen="\033[1;47;1;34m"; $TIME=`date "+%H:%M"`; date_default_timezone_set("Asia/Ho_Chi_Minh");

$useragent="Mozilla/5.0 (Linux; Android 10; SM-J600G) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.106 Mobile Safari/537.36";
//Time
echo $banner;
sleep(1);;;;
    $user = $_SESSION["username"];
    $xu = file_get_contents('https://traodoisub.com/scr/test3.php?user='.$user);
echo "\n";
usleep(100000);
$weekday = date("l");
$ngay = date("d");
$thang = date("m");
$nam = date("Y");
$weekday = strtolower($weekday);
    switch($weekday) {
        case 'monday':
            $weekday = "\033[1;33mThứ\033[1;36m Hai";
            break;
        case 'tuesday':
            $weekday = "\033[1;33mThứ\033[1;36m Ba";
            break;
        case 'wednesday':
            $weekday = "\033[1;33mThứ \033[1;36mTư";
            break;
        case 'thursday':
            $weekday = "\033[1;33mThứ \033[1;36mNăm";
            break;
        case 'friday':
            $weekday = "\033[1;33mThứ\033[1;36m Sáu";
            break;
        case 'saturday':
            $weekday = "\033[1;33mThứ \033[1;36mBảy";
            break;
        default:
            $weekday = "\033[1;33mChủ \033[1;36mNhật";
            break;
    }
//config
@system('clear');
$_SESSION['check'] = file_exists("log.txt");
if ($_SESSION['check'] =='1'){
echo  $green."Bạn Đã Đăng Nhập Trước Đó! Nhấn$yellow Enter$green Để Tiếp Tục, Nhập$red No \033[1;32mĐể Dùng Acc Mới: ";
$_SESSION['nhap'] = trim(fgets(STDIN));
if ($_SESSION['nhap'] !='no' and $_SESSION['nhap'] != 'No' and $_SESSION['nhap'] !=''){
echo $white."~ ".$red."Lựa chọn không xác định\n";
exit;
}
if ($_SESSION['nhap'] =='no' or $_SESSION['nhap'] =='No'){
$my = fopen("log.txt", "w+");
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Nhập Access_Token TDS: ";
$tokentds =trim(fgets(STDIN));
$arr = array("tokentds"=> $tokentds);
fwrite($my,json_encode($arr));
    $my = file("log.txt");
$bb = file_get_contents('log.txt');
$cc =json_decode($bb);
}
if ($_SESSION['nhap'] == ''){
$bb = file_get_contents("log.txt");
$cc =json_decode($bb);
$tokentds = $cc->{"tokentds"};

}
} else {
$my = fopen("log.txt","w+");
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Nhập Access_Token TDS: ";
$tokentds =trim(fgets(STDIN));
$arr = array("tokentds"=> $tokentds);
fwrite($my,json_encode($arr));
}
$m = login($tokentds);
$mm = json_decode($m);
$sss = $mm->{"success"};
if ($sss=='200'){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Đăng Nhập Thành Công\n";
  // get xu
  $user = $mm->{"data"}->{"user"};
  $xu = $mm->{"data"}->{"xu"};
}else{
echo $res."~".$yellow."[".$red."✖".$yellow."]".$res." =>".$red." Đăng Nhập Thất Bại\n";
	exit; 
}
if ($chedo ==1 or $chedo ==3){
  $luong = 1;
} else{
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Nhập Số Tài Khoản Muốn Treo: \033[1;36m";
$luong=trim(fgets(STDIN));
if ($luong<1){exit($red."\033[1;37m~\033[1;31m Lựa Chọn Không Xác Định\n");}
}
$c=1;$thu=1;
$mangcookie =[];
if ($chedo <3 ){
for($b=1;$b<=$luong;$b++){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$yellow." Nhập Cookie Thứ ".$thu.":$white ";
    $cooki[$c]=trim(fgets(STDIN));
    $ch=curl_init();
    $cookie=$cooki[$c];
$access = cookie($cookie,$useragent);
if (explode('\",\"useLocalFilePreview',explode('accessToken\":\"', $access)[1])[0])
{
        array_push($mangcookie,$cookie);
	             $c++;
	            $thu++;
}else{echo $white."~ ".$red."Cookie Die! Hãy Kiểm Tra Lại\n";$b--;}
}
} else {
for($b=1;$b<=$luong;$b++){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$yellow." Nhập Token Thứ ".$thu.":$white ";
    $cooki[$c]=trim(fgets(STDIN));
    $ch=curl_init();
    $cookie=$cooki[$c];
$access_token = $cookie;
if(json_decode(file_get_contents('https://graph.facebook.com/me/?access_token='.$access_token))->{'id'}){
        array_push($mangcookie,$cookie);
	             $c++;
	            $thu++;
}else{
  echo $white."~ ".$red."Token Die! Hãy Kiểm Tra Lại\n";$b--;}
} 
  
}


if($luong==1){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Sau Bao Nhiêu Nhiệm Vụ Bật Kháng Block:\033[1;33m ";
} else{
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Đổi Cấu Hình Sau: \033[1;33m";
}
$doi=trim(fgets(STDIN));
if ($doi<1){
  exit($red."\033[1;37m~\033[1;31m Lựa Chọn Không Xác Định\n");
}
if($luong==1){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Delay Kháng Block:\033[1;33m ";
  $dl=trim(fgets(STDIN));
}
@system('clear');
echo $banner."           
\033[0;36m╔═══════════════════════════════════════════════╗
\033[0;36m║\033[0;32m====> TOOl TRAODOISUB BY LTD☚ 🌸<====   \033[0;36m ║                          
\033[0;36m     ╔═══════════════════════════════╗
\033[0;36m     ║ 🔰\033[0;33mFacebook🔰: Hoàng Hải Long ✔\033[0;36m ║
\033[0;36m     ╚═══════════════════════════════╝

\033[0;36m║\033[0;35m=> [ CHÚC MỪNG BẠN ĐÃ LOGIN THÀNH CÔNG🌸 ] <=   \033[0;36m ║
\033[0;36m╚═══════════════════════════════════════════════╝


\n"; 
sleep(1);;;;

echo $banner;
echo $white."                $maufulldo 🌺Tool TDS Vip 🌺 Copyright © 2021 By Hoàng Hải Long🌺 $ngblack\n";
for($v=0;$v<= 12;$v++){
    echo "\033[1;37m- ";usleep(15000);
    echo "\033[1;33m- ";usleep(15000);
}
echo "\033[1;37m- ";usleep(15000);
echo "\033[1;33m-";usleep(15000);
echo"\n";
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$yellow." Tên Tài Khoản: $green".$user."\n";
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$pink." Số Nick Chạy:$green $luong\n";
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$cuan." Xu Hiện Có:$yellow $xu\n";
for($v=0;$v<= 12;$v++){
    echo "\033[1;37m- ";usleep(15000);
    echo "\033[1;33m- ";usleep(15000);
}
echo "\033[1;37m- ";usleep(15000);
echo "\033[1;33m-";usleep(15000);
echo"\n";
$listnv = [];
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Bật Auto Follow$white (y/n): $yellow";
  $chon1=trim(fgets(STDIN));
  if ($chon1 == 'y' or $chon1 == 'Y'){
    array_push($listnv,'sub');}
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Bật Auto Like$white (y/n): $yellow";
  $chon2=trim(fgets(STDIN));
  if ($chon2 == 'y' or $chon2 == 'Y'){
    array_push($listnv,'like');}
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Bật Auto Comment$white (y/n): $yellow";
  $chon3=trim(fgets(STDIN));
  if ($chon3 == 'y' or $chon3 == 'Y'){
    array_push($listnv,'cmt');}
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Bật Auto Share$white (y/n): $yellow";
  $chon4=trim(fgets(STDIN));
  if ($chon4 == 'y' or $chon4 == 'Y'){
    array_push($listnv,'share');}
if ($chedo < 3){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Bật Auto Like Page$white (y/n): $yellow";
  $chon4=trim(fgets(STDIN));
  if ($chon4 == 'y' or $chon4 == 'Y'){
    array_push($listnv,'page');}
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Bật Auto Cảm Xúc$white (y/n): $yellow";
  $chon4=trim(fgets(STDIN));
  if ($chon4 == 'y' or $chon4 == 'Y'){
    array_push($listnv,'cx');}
}
  if (count($listnv) == 0){exit($red."Chọn Ít Nhất 1 Nhiệm Vụ\n");}
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Nhập Delay Nhiệm Vụ: $yellow";
  $timedelay=trim(fgets(STDIN));
for($v=0;$v<= 12;$v++){
    echo "\033[1;37m- ";usleep(15000);
    echo "\033[1;33m- ";usleep(15000);
}
echo "\033[1;37m- ";usleep(15000);
echo "\033[1;33m-";usleep(15000);
echo"\n";
$q=1;
while ($o <= $_SESSION['i']){
for($l=0;$l<count($mangcookie);$l++){
$cookie = $mangcookie[$l];
if ($chedo < 3){
$access = cookie($cookie,$useragent);
$access_token = explode('\",\"useLocalFilePreview',explode('accessToken\":\"', $access)[1])[0];
} else {
  $access_token = $cookie;
}
if(json_decode(file_get_contents('https://graph.facebook.com/me/?access_token='.$access_token))->{'id'}){
  $idfb = json_decode(file_get_contents('https://graph.facebook.com/me/?access_token='.$access_token))->{'id'};
  $tenfb = json_decode(file_get_contents('https://graph.facebook.com/me/?access_token='.$access_token))->{'name'};
}else{
  echo "                                     \r";
  echo $res."~".$yellow."[".$red."✖".$yellow."]".$res." =>".$red." Thất Bại, FB Đã Bị Die, Hãy Xem Lại\n";
  exit; 
}
$h = datnick($idfb,$tokentds);
if ($h == '200'){
echo "                                                    \r";
echo $green."Đang Dùng FB: $yellow".$tenfb." \033[1;32mID:\033[1;37m ".$idfb."\n";
@system('clear');
@system('clear');
echo $banner;
 echo $luc, "   

       \033[1;92m                   __         ______     __   __     ______        __         ______   _____    ";

       sleep(1);
       echo $luc, "
       \033[1;91m                  /\ \       /\  __ \   /\ `-.\ \   /\  ___\      /\ \       /\__  _\ /\  __ \  ";
       sleep(1);
       echo $luc, "
       \033[1;93m                  \ \ \____  \ \ \/\ \  \ \ \-.  \  \ \ \__ \     \ \ \____  \/_/\ \/ \ \ \/\ \ ";
       sleep(1);
       echo $luc, "               
       \033[1;95m                   \ \_____\  \ \_____\  \ \_\\``\_\  \ \_____\     \ \_____\    \ \_\  \ \____- ";
       sleep(1);
       echo $luc, "  
       \033[1;96m                    \/_____/   \/_____/   \/_/ \/_/   \/_____/      \/_____/     \/_/   \/____/ ";
       sleep(1);
       echo $luc, "
       \033[1;97m                                                                                                \n";
       
sleep(1);
$banner="\r";
echo $redb."▬🌺🌺";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."🌺🌺▬";usleep(50000);echo"\n";

echo"\033[0;32m╭───────────────────────────────────╮
  [🌟]● My Name's : Hoàng Hải Long ✔
  [🌟]● Youtube🌼   :   Zenitsu EDM\n";
echo"\033[1;33m  [⚡]● Tool: Trao Đổi Sub° 
  [🌟]● Trạng Thái: Đang Hoạt Động.
  [🌟]● Tool Free Không Đem Bán
╰───────────────────────────────────╯\n";

      
sleep(1);;;;

echo $redb."▬🌺🌺";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."🌺🌺▬";usleep(50000);echo"\n";
echo"        \033[0;41m\033[1;32mHôm Nay Là \033[0;41m\033[1;37m➜\033[0;41m ";echo"\033[0;41m\033[1;36m$weekday ";echo"\033[0;41m\033[1;33mNgày ";
echo"\033[0;41m\033[1;36m$ngay ";echo"\033[0;41m\033[1;33mTháng ";
echo"\033[0;41m\033[1;36m$thang ";echo"\033[0;41m\033[1;33mNăm ";
echo"\033[0;41m\033[1;36m$nam$end";echo"\n";usleep(50000);
echo $redb."▬🌺🌺";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."▬";usleep(50000);echo $redb."▬";usleep(50000);echo $whiteb."🌺🌺▬";usleep(50000);echo"\n\n";

        $i=1;
        $max=0;
while($i<10){
  $rand = $listnv[array_rand($listnv,1)];
  if ($rand == 'like'){
    $list = getnv1('like',$tokentds);
    $check = count($list);
    if($check==0){
    echo "                                                      \r";
     echo $white."~ ".$red."Hết Nhiệm Vụ Like\r";
     #continue;
    }
    
    for($k=0;$k<$check;$k++) {
    $id = $list[$k]->{"id"};
    $g = like($access_token,$id,$cookie);
    if ($g->{'error'}->{'code'} == 368){
          echo "                                                      \r";
          echo $white."~ ".$red."Nick Đã Bị Block\n";
          array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
    $ck= nhantien('LIKE',$id,$tokentds);
      $s = json_decode($ck)->{"success"};
			if ($s == '200'){
			 $t = random_int(31,37);
    $mau = "\e[1;$t"."m";
      $max=$max+1;
      $stt=$stt+1;
      $xu = $xu + 200;
      echo "\r";
      echo "                                              \r";
      echo $yellow."[$stt]".$red." ● ".$cyan; usleep(10000);
      echo date("H:i:s"); usleep(10000);
      echo $red." ●$mau LIKE$red ● $white"; usleep(10000);
      echo $id."$red ● $yellow"; usleep(10000);
      echo $xu." xu\n";
      loadtime($timedelay);
      if ($max==$doi){
           $max=0;
           break;
          }
    } // nháº­n tiá»n
    } // foreach
    
    if($check!=0){
    if($max==0){
          if(count($mangcookie)==1){
          echo "                                                      \r";
           for($j = $dl;$j> 0;$j--){
             echo $green."Đang Chờ Delay Tránh Block$yellow $j Giây";
             sleep(1);
             echo "\r";
             echo "                                                      \r";
           }
          }else{
          break;}
        }
        if($m==1){
      $m=0;
      break; 
    }
    }
  }
  if ($rand == 'sub'){
		$list = getnv1('follow',$tokentds);
    $check = count($list);
    if($check==0){
      echo "                                                      \r";
 echo $white."~ ".$red."Hết Nhiệm Vụ Follow\r";
    }
    
    for($k=0;$k<$check;$k++) {
    $id = $list[$k]->{"id"};
    $g = follow($access_token,$id,$cookie);
    if ($g->{'error'}->{'code'} == 190){
            	echo "                                                      \r";
            echo $white."~ ".$red."Thất Bại! FB Bị Văng Khỏi Web\n";
            array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
    if ($g->{'error'}->{'code'} == 368){
          echo "                                                      \r";
          echo $white."~ ".$red."Đã Bị Block\n";
          array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
			$ck= nhantien('FOLLOW',$id,$tokentds);
      $s = json_decode($ck)->{"success"};
			if ($s == '200'){
			 $t = random_int(31,37);
    $mau = "\e[1;$t"."m";
      $max=$max+1;
      $stt=$stt+1;
      $xu = $xu + 600;
      echo "\r";
      echo "                                              \r";
      echo $yellow."[$stt]".$red." ● ".$cyan; usleep(10000);
      echo date("H:i:s"); usleep(10000);
      echo $red." ●$mau FOLLOW$red ● $white"; usleep(10000);
      echo $id."$red ● $yellow"; usleep(10000);
      echo $xu." xu\n";
      loadtime($timedelay);
      if ($max==$doi){
           $max=0;
           break;
          }
    } // nháº­n tiá»n
    } // foreach
  
    if($check!=0){
    if($max==0){
          if(count($mangcookie)==1){
          echo "                                                      \r";
           for($j = $dl;$j> 0;$j--){
             echo $green."Đang Chờ Delay Tránh Block$yellow $j Giây";
             sleep(1);
             echo "\r";
             echo "                                                      \r";
           }
          }else{
          break;}
        }  
    if($m==1){
      $m=0;
      break; 
    }
  
    }
  }
  if ($rand == 'cmt'){
    $list = getnv1('comment',$tokentds);
    $check = count($list);
    if($check==0){
     echo "                                                      \r";
     echo $white."~ ".$red."Hết Nhiệm Vụ Comment\r";
    }
    
    for($k=0;$k<$check;$k++) {
    $uid = $list[$k]->{"id"};
    $msg = $list[$k]->{"msg"};
    $g = cmt($access_token,$uid,$cookie,$msg);
    if ($g->{'error'}->{'code'} == 190){
            	echo "                                                      \r";
            echo $white."~ ".$red."Thất Bại! FB Bị Văng Khỏi Web\n";
            array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
    if ($g->{'error'}->{'code'} == 368){
          echo "                                                      \r";
          echo $white."~ ".$red."Đã Bị Block\n";
          array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
    $ck= nhantien('COMMENT',$uid,$tokentds);
      $s = json_decode($ck)->{"success"};
			if ($s == '200'){
			  $t = random_int(31,37);
    $mau = "\e[1;$t"."m";
      $max=$max+1;
      $stt=$stt+1;
      $xu = $xu + 600;
      echo "\r";
      echo "                                              \r";
      echo $yellow."[$stt]".$red." ● ".$cyan; usleep(10000);
      echo date("H:i:s"); usleep(10000);
      echo $red." ●$mau CMT$red ● $white"; usleep(10000);
      echo $uid."$red ● $yellow"; usleep(10000);
      echo $xu." xu\n";
      loadtime($timedelay);
      if ($max==$doi){
           $max=0;
           break;
          }
    } // nháº­n tiá»n
    } // foreach
    
    if($check!=0){
    if($max==0){
          if(count($mangcookie)==1){
          echo "                                                    \r";
           for($j = $dl;$j> 0;$j--){
             echo $green."Đang Chờ Delay Tránh Block$yellow $j Giây";
             sleep(1);
             echo "\r";
             echo "                                                      \r";
           }
          }else{
          break;}
        } 
        if($m==1){
      $m=0;
      break; 
    }
    }
  }
  if ($rand == 'page'){
    $list = getnv1('page',$tokentds);
    $check = count($list);
    if($check==0){
     echo "                                                      \r";
     echo $white."~ ".$red."Hết Nhiệm Vụ Like Page\r";
    }
    
    for($k=0;$k<$check;$k++) {
    $id = $list[$k]->{"id"};
    $g = page($id,$cookie);
    if ($g->{'error'}->{'code'} == 190){
            	echo "                                                      \r";
            echo $white."~ ".$red."Thất Bại! FB Bị Văng Khỏi Web\n";
            array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
    if ($g->{'error'}->{'code'} == 368){
          echo "                                                      \r";
          echo $white."~ ".$red."Đã Bị Block\n";
          array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
    $ck= nhantien('PAGE',$id,$tokentds);
      $s = json_decode($ck)->{"success"};
			if ($s == '200'){
			  $t = random_int(31,37);
    $mau = "\e[1;$t"."m";
      $max=$max+1;
      $stt=$stt+1;
      $xu = $xu + 600;
      echo "\r";
      echo "                                              \r";
      echo $yellow."[$stt]".$red." ● ".$cyan; usleep(10000);
      echo date("H:i:s"); usleep(10000);
      echo $red." ●$mau PAGE$red ● $white"; usleep(10000);
      echo $id."$red ● $yellow"; usleep(10000);
      echo $xu." xu\n";
      loadtime($timedelay);
      if ($max==$doi){
           $max=0;
           break;
          }
    } // nháº­n tiá»n
    } // foreach
    
    if($check!=0){
    if($max==0){
          if(count($mangcookie)==1){
          echo "                                                    \r";
           for($j = $dl;$j> 0;$j--){
             echo $green."Đang Chờ Delay Tránh Block$yellow $j Giây";
             sleep(1);
             echo "\r";
             echo "                                                      \r";
           }
          }else{
          break;}
        } 
        if($m==1){
      $m=0;
      break; 
    }
    }
  }
  if ($rand == 'share'){
    $list = getnv1('share',$tokentds);
    $check = count($list);
    if($check==0){
     echo "                                                      \r";
     echo $white."~ ".$red."Hết Nhiệm Vụ Share\r";
    }
    for($k=0;$k<$check;$k++) {
    $id = $list[$k]->{"id"};
    $g = share($id,$access_token);
    $ck= nhantien('SHARE',$id,$tokentds);
      $s = json_decode($ck)->{"success"};
			if ($s == '200'){
			  $t = random_int(31,37);
    $mau = "\e[1;$t"."m";
      $max=$max+1;
      $stt=$stt+1;
      $xu = $xu + 800;
      echo "\r";
      echo "                                              \r";
      echo $yellow."[$stt]".$red." ● ".$cyan; usleep(10000);
      echo date("H:i:s"); usleep(10000);
      echo $red." ●$mau SHARE$red ● $white"; usleep(10000);
      echo $id."$red ● $yellow"; usleep(10000);
      echo $xu." xu\n";
      loadtime($timedelay);
      if ($max==$doi){
           $max=0;
           break;
          }
    } // nháº­n tiá»n
    } // foreach
    
    if($check!=0){
    if($max==0){
          if(count($mangcookie)==1){
          echo "                                                    \r";
           for($j = $dl;$j> 0;$j--){
             echo $green."Đang Chờ Delay Tránh Block$yellow $j Giây";
             sleep(1);
             echo "\r";
             echo "                                                      \r";
           }
          }else{
          break;}
        } 
        if($m==1){
      $m=0;
      break; 
    }
    }
  }
  if ($rand == 'group'){
    $list = getnv1('group',$tokentds);
    $check = count($list);
    if($check==0){
     echo "                                                      \r";
     echo $white."~ ".$red."Hết Nhiệm Vụ Join Group\r";
    }
    for($k=0;$k<$check;$k++) {
    $id = $list[$k]->{"id"};
    $g = joingr($id,$cookie);
    $ck= nhantien('GROUP',$id,$tokentds);
      $s = json_decode($ck)->{"success"};
			if ($s == '200'){
			  $t = random_int(31,37);
    $mau = "\e[1;$t"."m";
      $max=$max+1;
      $stt=$stt+1;
      $xu = $xu + 1400;
      echo "\r";
      echo "                                              \r";
      echo $yellow."[$stt]".$red." ● ".$cyan; usleep(10000);
      echo date("H:i:s"); usleep(10000);
      echo $red." ●$mau GROUP$red ● $white"; usleep(10000);
      echo $id."$red ● $yellow"; usleep(10000);
      echo $xu." xu\n";
      loadtime($timedelay);
      if ($max==$doi){
           $max=0;
           break;
          }
    } // nháº­n tiá»n
    else{ echo "Lá»—i \n"; }
    } // foreach
    
    if($check!=0){
    if($max==0){
          if(count($mangcookie)==1){
          echo "                                                    \r";
           for($j = $dl;$j> 0;$j--){
             echo $green."Đang Chờ Delay Tránh Block$yellow $j Giây";
             sleep(1);
             echo "\r";
             echo "                                                      \r";
           }
          }else{
          break;}
        } 
        if($m==1){
      $m=0;
      break; 
    }
    }
  }
  if ($rand == 'cx'){
    $list = getnv1('reaction',$tokentds);
    $check = count($list);
    if($check==0){
     echo "                                                      \r";
     echo $white."~ ".$red."Hết Nhiệm Vụ Cảm Xúc\r";
    #continue;
    }
    
    for($k=0;$k<$check;$k++) {
    $id = $list[$k]->{"id"};
    $type = $list[$k]->{"type"};
    $g = camxuc($id,$type,$cookie);
    if ($g->{'error'}->{'code'} == 190){
            	echo "                                                      \r";
            echo $white."~ ".$red."Thất Bại! FB Bị Văng Khỏi Web\n";
            array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
    if ($g->{'error'}->{'code'} == 368){
          echo "                                                      \r";
          echo $white."~ ".$red."Đã Bị Block\n";
          array_splice($mangcookie,$l,1);
            $m = 1;
            break;
    }
	$ck= nhantien($type,$id,$tokentds);
      $s = json_decode($ck)->{"success"};
			if ($s == '200'){
			  $t = random_int(31,37);
    $mau = "\e[1;$t"."m";
      $max=$max+1;
      $stt=$stt+1;
      $xu = $xu + 400;
      echo "\r";
      echo "                                              \r";
      echo $yellow."[$stt]".$red." ● ".$cyan; usleep(10000);
      echo date("H:i:s"); usleep(10000);
      echo $red." ●$mau $type$red ● $white"; usleep(10000);
      echo $id."$red ● $yellow"; usleep(10000);
      echo $xu." xu\n";
      loadtime($timedelay);
      if ($max==$doi){
           $max=0;
           break;
          }
    } // nháº­n tiá»n
    } // foreach
    
    if($check!=0){
    if($max==0){
          if(count($mangcookie)==1){
          echo "                                                    \r";
           for($j = $dl;$j> 0;$j--){
             echo $green."Đang Chờ Delay Tránh Block$yellow $j Giây";
             sleep(1);
             echo "\r";
             echo "                                                      \r";
           }
          }else{
          break;}
        }  
      if($m==1){
      $m=0;
      break; 
    }
    }
  }
  
} //vĂ²ng while trong

} //vĂ²ng cáº¥u hĂ¬nh
else{ exit($red."Cấu Hình Thất Bại, Hãy Thêm FB:\033[1;32m $tenfb $red"."Vào Cấu Hình\n"); }
} // vĂ²ng for
if (count($mangcookie)==1 && empty($dl)){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Vẫn Còn 1 Acc. Nhập Delay Kháng Block: ";
  $dl=trim(fgets(STDIN));
}
if (count($mangcookie)==0){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Tất Cả Cookie Để Die, Hãy Nhập Lại:\n";
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Nhập Số Nick Cần Treo:\033[1;36m ";
$luong=trim(fgets(STDIN));
if ($luong<1){exit($red."\033[1;37m~\033[1;31m Lựa Chọn Không Xác Định\n");}
$c=1;$thu=1;
if ($chedo <3 ){
for($b=1;$b<=$luong;$b++){
    echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$yellow." Nhập Cookie Thứ ".$thu.":$white ";
    $cooki[$c]=trim(fgets(STDIN));
    $ch=curl_init();
    $cookie=$cooki[$c];
$access = cookie($cookie,$useragent);
if (explode('\",\"useLocalFilePreview',explode('accessToken\":\"', $access)[1])[0])
{
        array_push($mangcookie,$cookie);
	             $c++;
	            $thu++;
}else{echo $white."~ ".$red."Cookie Không Hợp Lệ, Hãy Kiểm Tra Lại\n";$b--;}
}
} else {
for($b=1;$b<=$luong;$b++){
    echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$yellow." NhậpToken Thứ ".$thu.":$white ";
    $cooki[$c]=trim(fgets(STDIN));
    $ch=curl_init();
    $cookie=$cooki[$c];
$access_token = $cookie;
if(json_decode(file_get_contents('https://graph.facebook.com/me/?access_token='.$access_token))->{'id'}){
        array_push($mangcookie,$cookie);
	             $c++;
	            $thu++;
}else{
  echo $white."~ ".$red."Token Không Đúng, Hãy Nhập Lại\n";$b--;
}
} 
  
}
if (count($mangcookie)==1 && empty($dl)){
echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Sau Bao Nhiêu Nhiệm Vụ Bật Kháng Block:\033[1;32m ";
  $doi=trim(fgets(STDIN));
  echo $res."~".$red."[".$green."✔".$red."]".$res." =>".$green." Delay Kháng Block: ";
  $dl=trim(fgets(STDIN));
}
} // die háº¿t cookie
} // 
function cookie($cookie,$useragent){
$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://m.facebook.com/composer/ocelot/async_loader/?publisher=feed');
$head[] = "Connection: keep-alive";
$head[] = "Keep-Alive: 300";
$head[] = "authority: m.facebook.com";
$head[] = "ccept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7";
$head[] = "accept-language: vi-VN,vi;q=0.9,fr-FR;q=0.8,fr;q=0.7,en-US;q=0.6,en;q=0.5";
$head[] = "cache-control: max-age=0";
$head[] = "upgrade-insecure-requests: 1";
$head[] = "accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9";
$head[] = "sec-fetch-site: none";
$head[] = "sec-fetch-mode: navigate";
$head[] = "sec-fetch-user: ?1";
$head[] = "sec-fetch-dest: document";
curl_setopt($ch, CURLOPT_USERAGENT,$useragent );
curl_setopt($ch, CURLOPT_ENCODING, '');
curl_setopt($ch, CURLOPT_COOKIE, $cookie);
curl_setopt($ch, CURLOPT_HTTPHEADER, $head);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
curl_setopt($ch, CURLOPT_TIMEOUT, 60);
curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 60);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, TRUE);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Expect:'));
$access = curl_exec($ch);
curl_close($ch);
return $access;
}
function follow($access_token,$id,$cookie){
	$ch=curl_init();
	curl_setopt($ch, CURLOPT_URL, 'https://graph.facebook.com/'.$id.'/subscribers');
	$head[] = "Connection: keep-alive";
	$head[] = "Keep-Alive: 300";
	$head[] = "authority: m.facebook.com";
	$head[] = "ccept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7";
	$head[] = "accept-language: vi-VN,vi;q=0.9,fr-FR;q=0.8,fr;q=0.7,en-US;q=0.6,en;q=0.5";
	$head[] = "cache-control: max-age=0";
	$head[] = "upgrade-insecure-requests: 1";
	$head[] = "accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9";
	$head[] = "sec-fetch-site: none";
	$head[] = "sec-fetch-mode: navigate";
	$head[] = "sec-fetch-user: ?1";
	$head[] = "sec-fetch-dest: document";
	curl_setopt($ch, CURLOPT_USERAGENT, 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.135 Safari/537.36');
	curl_setopt($ch, CURLOPT_ENCODING, '');
	curl_setopt($ch, CURLOPT_COOKIE, $cookie);
	curl_setopt($ch, CURLOPT_HTTPHEADER, $head);
	curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
	curl_setopt($ch, CURLOPT_TIMEOUT, 60);
	curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 60);
	curl_setopt($ch, CURLOPT_FOLLOWLOCATION, TRUE);
	curl_setopt($ch, CURLOPT_HTTPHEADER, array('Expect:'));
	$data = array('access_token' => $access_token);
	curl_setopt($ch, CURLOPT_POST,count($data));
	curl_setopt($ch, CURLOPT_POSTFIELDS,$data);
	$access = curl_exec($ch);
	curl_close($ch);
	return json_decode($access);
}
function like($access_token,$id,$cookie){
  $ch=curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://graph.facebook.com/'.$id.'/likes');
  $head[] = "Connection: keep-alive";
  $head[] = "Keep-Alive: 300";
  $head[] = "authority: m.facebook.com";
  $head[] = "ccept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7";
  $head[] = "accept-language: vi-VN,vi;q=0.9,fr-FR;q=0.8,fr;q=0.7,en-US;q=0.6,en;q=0.5";
  $head[] = "cache-control: max-age=0";
  $head[] = "upgrade-insecure-requests: 1";
  $head[] = "accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9";
  $head[] = "sec-fetch-site: none";
  $head[] = "sec-fetch-mode: navigate";
  $head[] = "sec-fetch-user: ?1";
  $head[] = "sec-fetch-dest: document";
  curl_setopt($ch, CURLOPT_USERAGENT, 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.135 Safari/537.36');
  curl_setopt($ch, CURLOPT_ENCODING, '');
  curl_setopt($ch, CURLOPT_COOKIE, $cookie);
  curl_setopt($ch, CURLOPT_HTTPHEADER, $head);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
  curl_setopt($ch, CURLOPT_TIMEOUT, 60);
  curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 60);
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, TRUE);
  curl_setopt($ch, CURLOPT_HTTPHEADER, array('Expect:'));
  $data = array('access_token' => $access_token);
  curl_setopt($ch, CURLOPT_POST,count($data));
  curl_setopt($ch, CURLOPT_POSTFIELDS,$data);
  $access = curl_exec($ch);
  curl_close($ch);
  return json_decode($access);
}
function cmt($access_token,$id,$cookie,$msg){
	$ch=curl_init();
	curl_setopt($ch, CURLOPT_URL, 'https://graph.facebook.com/'.$id.'/comments');
	$head[] = "Connection: keep-alive";
	$head[] = "Keep-Alive: 300";
	$head[] = "authority: m.facebook.com";
	$head[] = "ccept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7";
	$head[] = "accept-language: vi-VN,vi;q=0.9,fr-FR;q=0.8,fr;q=0.7,en-US;q=0.6,en;q=0.5";
	$head[] = "cache-control: max-age=0";
	$head[] = "upgrade-insecure-requests: 1";
	$head[] = "accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9";
	$head[] = "sec-fetch-site:";
	$head[] = "sec-fetch-mode: navigate";
	$head[] = "sec-fetch-user: ?1";
	$head[] = "sec-fetch-dest: document";
	curl_setopt($ch, CURLOPT_USERAGENT, 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.135 Safari/537.36');
	curl_setopt($ch, CURLOPT_ENCODING, '');
	curl_setopt($ch, CURLOPT_COOKIE, $cookie);
	curl_setopt($ch, CURLOPT_HTTPHEADER, $head);
	curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
	curl_setopt($ch, CURLOPT_TIMEOUT, 60);
	curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 60);
	curl_setopt($ch, CURLOPT_FOLLOWLOCATION, TRUE);
	curl_setopt($ch, CURLOPT_HTTPHEADER, array('Expect:'));
	$data = array('message' => $msg,'access_token' => $access_token);
	curl_setopt($ch, CURLOPT_POST,count($data));
	curl_setopt($ch, CURLOPT_POSTFIELDS,$data);
	$access = curl_exec($ch);
	curl_close($ch);
	return json_decode($access);
}
function page($id,$cookie){
	$ch = curl_init();
	curl_setopt($ch, CURLOPT_URL, 'https://mbasic.facebook.com/'.$id);
	$head[] = "Connection: keep-alive";
	$head[] = "Keep-Alive: 300";
	$head[] = "Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7";
	$head[] = "Accept-Language: en-us,en;q=0.5";
	curl_setopt($ch, CURLOPT_USERAGENT, 'Opera/9.80 (Windows NT 6.0) Presto/2.12.388 Version/12.14');
	curl_setopt($ch, CURLOPT_ENCODING, '');
	curl_setopt($ch, CURLOPT_COOKIE, $cookie);
	curl_setopt($ch, CURLOPT_HTTPHEADER, $head);
	curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, FALSE);
	curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
	curl_setopt($ch, CURLOPT_TIMEOUT, 60);
	curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 60);
	curl_setopt($ch, CURLOPT_FOLLOWLOCATION, TRUE);
	curl_setopt($ch, CURLOPT_HTTPHEADER, array('Expect
	:'));
	$page = curl_exec($ch);
	if (explode('&amp;refid=',explode('pageSuggestionsOnLiking=1&amp;gfid=',$page)[1])[0]){
		$get = explode('&amp;refid=',explode('pageSuggestionsOnLiking=1&amp;gfid=',$page)[1])[0];
		$link = 'https://mbasic.facebook.com/a/profile.php?fan&id='.$id.'&origin=page_profile&pageSuggestionsOnLiking=1&gfid='.$get.'&refid=17';
		curl_setopt($ch, CURLOPT_URL, $link);
		curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
		curl_exec($ch);
	}	
	curl_close($ch);

}
function getnv1($loai,$token){
	$list = file_get_contents('http://tttoriginal.tk/tds/getnv1.php?token='.$token.'&loai='.$loai);
	return json_decode($list);
}
function camxuc($id,$type,$cookie){
	$ch = curl_init();
	if(strpos($id,'_')){
		$uid = explode('_',$id, 2);
		$id2 = 'story.php?story_fbid='.$uid[1].'&id='.$uid[0];
	}else{
		$id2 = $id;
	}
	curl_setopt($ch, CURLOPT_URL, 'https://mbasic.facebook.com/'.$id2);
	$head[] = "Connection: keep-alive";
	$head[] = "Keep-Alive: 300";
	$head[] = "Accept-Charset: ISO-8859-1,utf-8;q=0.7,*;q=0.7";
	$head[] = "Accept-Language: en-us,en;q=0.5";
	curl_setopt($ch, CURLOPT_USERAGENT, 'Opera/9.80 (Windows NT 6.0) Presto/2.12.388 Version/12.14');
	curl_setopt($ch, CURLOPT_ENCODING, '');
	curl_setopt($ch, CURLOPT_COOKIE, $cookie);
	curl_setopt($ch, CURLOPT_HTTPHEADER, $head);
	curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, FALSE);
	curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
	curl_setopt($ch, CURLOPT_TIMEOUT, 60);
	curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 60);
	curl_setopt($ch, CURLOPT_FOLLOWLOCATION, TRUE);
	curl_setopt($ch, CURLOPT_HTTPHEADER, array('Expect
	:'));
	$page = curl_exec($ch);
	if ($id2 != $id && explode('&amp;origin_uri=',explode('amp;ft_id=',$page,2)[1],2)[0]){
		$get = explode('&amp;origin_uri=',explode('amp;ft_id=',$page,2)[1],2)[0];
	}else{
		$get = $id2;
	}
	$link = 'https://mbasic.facebook.com/reactions/picker/?is_permalink=1&ft_id='.$get;
	curl_setopt($ch, CURLOPT_URL, $link);
	curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
	$cx = curl_exec($ch);
	$haha = explode('<a href="',$cx);
	if ($type == 'LOVE'){
		$haha2 = explode('" style="display:block"',$haha[2])[0];
	}else if ($type == 'WOW'){
		$haha2 = explode('" style="display:block"',$haha[5])[0];
	}else if ($type == 'HAHA'){
		$haha2 = explode('" style="display:block"',$haha[4])[0];
	}else if ($type == 'SAD'){
		$haha2 = explode('" style="display:block"',$haha[6])[0];
	}else{
		$haha2 = explode('" style="display:block"',$haha[7])[0];
	}
	$link2 = html_entity_decode($haha2);	

	curl_setopt($ch, CURLOPT_URL, 'https://mbasic.facebook.com'.$link2);
	curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
	curl_exec($ch);
	curl_close($ch);
}
function loadtime($time){
        for ( $x = $time; $x--; $x ) {
       echo "                                                      \r";
echo "\e[1;32m● Vui Lòng Chờ <~>\e[1;37m |\e[1;31m● \e[1;32m● \e[1;33m● \e[1;34m● \e[1;35m● \e[1;37m| ".$x."\033[1;37m |\e[1;33mGiây";
usleep(170000);
echo "\r";
echo "                                                      \r";
echo "\e[1;36m● Vui Lòng Chờ <~>\e[1;37m |\e[1;33m● \e[1;34m● \e[1;35m● \e[1;36m● \e[1;31m● \e[1;37m| ".$x."\033[1;37m |\e[1;34m Giây";
       usleep(170000);
       echo "\r";
       echo "                                                      \r";
       echo "\e[1;34m● Vui Lòng Chờ <~>\e[1;37m |\e[1;34m● \e[1;35m● \e[1;36m● \e[1;31m● \e[1;33m● \e[1;37m| ".$x."\033[1;37m |\e[1;31m Giây";
       usleep(170000);
       echo "\r";
       echo "                                                      \r";
       echo "\e[1;33m● Vui Lòng Chờ <~>\e[1;37m |\e[1;35m● \e[1;36m● \e[1;31m● \e[1;33m● \e[1;34m● \e[1;37m| ".$x."\033[1;37m |\e[1;32m Giây";
       usleep(170000);
       echo "\r";
       echo "                                                      \r";
       echo "\e[1;31m● Vui Lòng Chờ <~>\e[1;37m |\e[1;33m● \e[1;32m● \e[1;31m● \e[1;35m● \e[1;36m●\e[1;37m| ".$x."\033[1;37m |\e[1;36m Giây";
       usleep(170000);
       echo "\r";
}
}
function datnick($id,$tokentds){
	$xxx = file_get_contents('https://traodoisub.com/api/?fields=run&id='.$id.'&access_token='.$tokentds);
	$h = json_decode($xxx)->{"success"};
	return $h; 
}
function nhantien($loai,$id,$tokentds){
  $nhan = file_get_contents('https://traodoisub.com/api/coin/?type='.$loai.'&id='.$id.'&access_token='.$tokentds);
  return $nhan; 
}
function login($tokentds){
  $login = file_get_contents("https://traodoisub.com/api/?fields=profile&access_token=".$tokentds);
  return $login;
}
function share($id,$token){
  $url= 'https://graph.facebook.com/me/feed?method=post&access_token='.$token.'&privacy={"value":"EVERYONE"}&link=https://www.facebook.com/'.$id.'/';
  $m = file_get_contents($url);
  return json_decode($m);
}


function joingr($id,$cookie){
  $ch = curl_init();
  $head_fb=array(
    "Host:mbasic.facebook.com",
    "cache-control:max-age=0",
    "upgrade-insecure-requests:1",
    "save-data:on",
    "user-agent:Mozilla/5.0 (Linux; Android 10; RMX1929) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.105 Mobile Safari/537.36",
    "accept:text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9",
    "sec-fetch-site:cross-site",
    "sec-fetch-mode:navigate",
    "sec-fetch-user:?1",
    "sec-fetch-dest:document",
    "accept-language:vi-VN,vi;q=0.9,fr-FR;q=0.8,fr;q=0.7,en-US;q=0.6,en;q=0.5",
    "cookie:".$cookie);
  curl_setopt_array ($ch, array (
  CURLOPT_URL => "https://mbasic.facebook.com/groups/$id?_rdr",
  CURLOPT_FOLLOWLOCATION => false,
  CURLOPT_RETURNTRANSFER => 1,
  CURLOPT_POST => 1,
  CURLOPT_HTTPGET => true,
  CURLOPT_SSL_VERIFYPEER => 0,
  CURLOPT_HTTPHEADER => $head_fb,
  CURLOPT_HEADER => true,
  CURLOPT_ENCODING => TRUE));
  $data = curl_exec($ch);
 // var_dump($data);
  if (strpos($data,"xs=deleted") == true){
  echo ( $red."Token die rá»“i\n");
  }
  $tĂ¬m =explode("/a/group/join/?",$data);
  $tĂ¬m1=explode('"',$tĂ¬m[1]);
  $fb=explode('name="fb_dtsg" value="',$data);
  $fb=explode('"',$fb[1]);
  $fbdtsg=htmlspecialchars_decode($fb[0]);
  $jaz=explode('name="jazoest" value="',$data);
  $jaz=explode('"',$jaz[1]);
  $url="https://mbasic.facebook.com/a/group/join/?".htmlspecialchars_decode($tĂ¬m1[0]);
  $data="fb_dtsg=$fbdtsg&jazoest=".$jaz[0];
  curl_setopt_array ($ch, array (
  CURLOPT_URL => $url,
  CURLOPT_RETURNTRANSFER => 1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => $data,
  CURLOPT_SSL_VERIFYPEER => 0,
  CURLOPT_HTTPHEADER => $head_fb));
  $xxx = curl_exec($ch);
}
