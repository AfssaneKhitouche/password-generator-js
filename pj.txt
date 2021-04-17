function password_generator( len ) {
    var length = (len)?(len):(10);
    var string = "abcdefghijklmnopqrstuvwxyz"; 
    var numeric = '0123456789';
    var punctuation = '!@#$%^&*()_+~`|}{[]\:;?><,./-=';
    var password = "";
    var character = "";
    while( password.length<length ) {
        let p1 = Math.ceil(string.length * Math.random()*Math.random());
        let p2 = Math.ceil(numeric.length * Math.random()*Math.random());
        let p3 = Math.ceil(punctuation.length * Math.random()*Math.random());
        let hold = string.charAt( p1 );
        hold = (password.length%2==0)?(hold.toUpperCase()):(hold);
        character += hold;
        character += numeric.charAt( p2 );
        character += punctuation.charAt( p3 );
        password = character;
    }
    password=password.split('').sort(function(){return 0.5-Math.random()}).join('');
    return password.substr(0,len);
}

console.log( password_generator() );
