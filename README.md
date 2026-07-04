<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <!-- 1. TÍTULO DE LA PÁGINA -->
    <title>¡Feliz Cumpleaños Victoria!</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght=700&family=Montserrat:wght=300;500;700&display=swap');
        *{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent;user-select:none}
        body{background:#0b090a;color:white;font-family:'Montserrat',sans-serif;height:100vh;width:100vw;display:flex;flex-direction:column;justify-content:center;align-items:center;overflow:hidden;perspective:1200px}
        canvas{position:fixed;inset:0;z-index:-1}
        
   /* Mensaje de cumpleaños con tonos dorados y fucsia */
        #msg{position:fixed;top:40px;font-family:'Dancing Script',cursive;font-size:2.8rem;color:#ffb703;text-shadow:0 0 20px #ffb703, 0 0 40px #ff0077;animation:p 2s infinite;z-index:10;width:100%;text-align:center;}
        @keyframes p{0%,100%{transform:scale(1)}50%{transform:scale(1.05)}}
        
   #escena{width:260px;height:260px;margin:0}
        #cubo{width:100%;height:100%;position:relative;transform-style:preserve-3d}
        .cara{position:absolute;width:260px;height:260px;border:2px solid rgba(255,183,3,0.6);box-shadow:0 0 15px rgba(255,183,3,0.3);background:#161a1d;display:flex;justify-content:center;align-items:center;overflow:hidden}
        .cara img{width:100%;height:100%;object-fit:cover;pointer-events:none}
        .f{transform:rotateY(0deg) translateZ(130px)}.b{transform:rotateY(180deg) translateZ(130px)}.r{transform:rotateY(90deg) translateZ(130px)}.l{transform:rotateY(-90deg) translateZ(130px)}.u{transform:rotateX(90deg) translateZ(130px)}.d{transform:rotateX(-90deg) translateZ(130px)}
        
  /* REPRODUCTOR */
        #pl{display:block;position:fixed;bottom:80px;width:95%;max-width:450px;padding:3px;border-radius:25px;overflow:hidden;z-index:100;box-shadow:0 10px 40px rgba(0,0,0,0.7)}
        #pl::before{content:'';position:absolute;top:-50%;left:-50%;width:200%;height:200%;background:conic-gradient(transparent,transparent,transparent,#ffb703);animation:rb 4s linear infinite;z-index:1}
        @keyframes rb{100%{transform:rotate(360deg)}}
        .pi{background:rgba(20,20,20,0.95);backdrop-filter:blur(20px);width:100%;height:100%;border-radius:23px;display:flex;align-items:center;gap:15px;padding:12px 20px;position:relative;z-index:2}
        
 .vin{width:50px;height:50px;flex-shrink:0;border-radius:50%;border:3px solid #222;overflow:hidden;position:relative;background:#000}
        .vin img{width:100%;height:100%;object-fit:cover}
        .vin.sp{animation:sp 4s linear infinite;border-color:#ffb703;box-shadow:0 0 15px #ffb703}@keyframes sp{100%{transform:rotate(360deg)}}
        #pb{background:white;color:#ffb703;border:none;width:45px;height:45px;flex-shrink:0;border-radius:50%;font-size:1.4rem;cursor:pointer;display:flex;justify-content:center;align-items:center;box-shadow:0 0 20px rgba(255,255,255,0.3);transition:0.2s;padding-left:4px}
        #pb.pg{padding-left:0;box-shadow:0 0 25px #ffb703;background:#ffb703;color:white}
        .ti{flex-grow:1;display:flex;flex-direction:column;gap:6px}
        .pa{width:100%;height:6px;background:rgba(255,255,255,0.1);border-radius:10px;cursor:pointer;position:relative}
        .bar{height:100%;width:0%;background:linear-gradient(90deg,#ffb703,#ff0077);border-radius:10px;position:relative;box-shadow:0 0 15px #ffb703}
        .td{font-size:0.7rem;color:#aaa;font-weight:600;display:flex;justify-content:space-between;letter-spacing:1px}
        .vz{display:flex;gap:3px;height:20px;align-items:flex-end}
        .vz.pg .vzb{animation:bn 0.5s infinite ease-in-out alternate}
        .vzb{width:3px;background:#ffb703;border-radius:3px}
        .vzb:nth-child(2){animation-delay:0.1s}.vzb:nth-child(3){animation-delay:0.2s}
        @keyframes bn{0%{height:3px;opacity:0.5}100%{height:20px;opacity:1;box-shadow:0 0 10px #ffb703}}
    </style>
</head>
<body>
    <canvas id="cv"></canvas>
    <!-- 2. MENSAJE PRINCIPAL DE CUMPLEAÑOS -->
    <div id="msg">¡Feliz Cumpleaños Victoria! 👑❤️</div>
      <div id="escena">
        <div id="cubo">
            <!-- 3. FOTOS DE VICTORIA O JUNTOS -->
            <!-- Reemplaza las URLs de abajo por tus fotos reales -->
            <div class="cara f"><img src="https://via.placeholder.com/260/ffb703/ffffff?text=Victoria+Foto+1" alt="Foto 1"></div>
            <div class="cara b"><img src="https://via.placeholder.com/260/ffb703/ffffff?text=Victoria+Foto+2" alt="Foto 2"></div>
            <div class="cara r"><img src="https://via.placeholder.com/260/ffb703/ffffff?text=Victoria+Foto+3" alt="Foto 3"></div>
            <div class="cara l"><img src="https://via.placeholder.com/260/ffb703/ffffff?text=Victoria+Foto+4" alt="Foto 4"></div>
            <div class="cara u"><img src="https://via.placeholder.com/260/ffb703/ffffff?text=Victoria+Foto+5" alt="Foto 5"></div>
            <div class="cara d"><img src="https://via.placeholder.com/260/ffb703/ffffff?text=Victoria+Foto+6" alt="Foto 6"></div>
        </div>
    </div>
<!-- REPRODUCTOR DE MÚSICA (CUMPLEAÑOS) -->
    <div id="pl">
        <div class="pi">
            <div class="vin" id="vi"><img src="https://via.placeholder.com/50/ff0077/ffffff?text=🎂" alt="Album"></div>
            <button id="pb">▶</button>
            <div class="ti">
                <!-- 4. DETALLES DE LA CANCIÓN -->
                <div style="font-size:0.85rem;font-weight:700;letter-spacing:0.5px" id="nt">Cumpleaños Feliz</div>
                <div style="font-size:0.7rem;color:#ffb703;font-weight:500" id="na">Para Victoria</div>
                <div class="pa" id="pG">
                    <div class="bar" id="bA"></div>
                </div>
                <div class="td">
                    <span id="ct">0:00</span>
                    <span id="du">0:00</span>
                </div>
            </div>
            <div class="vz" id="vA"><div class="vzb"></div><div class="vzb"></div><div class="vzb"></div></div>
        </div>
    </div>


<!-- 5. ENLACE DE LA CANCIÓN -->
 <audio id="au" src="cancion-cumple.mp3" preload="auto" loop></audio>

<script>
        // --- EFECTO DE DESTELLES / CONFETI DORADO DE FONDO ---
        const c=document.getElementById('cv'),$=c.getContext('2d');
        let w,h,p=[];
        function res(){w=c.width=window.innerWidth;h=c.height=window.innerHeight}
        window.addEventListener('resize',res);res();
        
        class Particula {
            constructor(){this.x=Math.random()*w;this.y=Math.random()*h;this.s=Math.random()*3+1;this.v=Math.random()*0.8+0.2;this.a=Math.random()}
            u(){this.y-=this.v;this.a+=0.01;if(this.y<0){this.y=h;this.x=Math.random()*w}}
            d(){$.fillStyle=`rgba(255, 183, 3, ${Math.abs(Math.sin(this.a))})`;$.beginPath();$.arc(this.x,this.y,this.s,0,Math.PI*2);$.fill()}
        }
        for(let i=0;i<50;i++)p.push(new Particula());
        function ani(){$.clearRect(0,0,w,h);p.forEach(pt=>{pt.u();pt.d()});requestAnimationFrame(ani)}
        ani();

        // --- CONTROL DEL CUBO ---
        const cb=document.getElementById('cubo');
        let rX=-20,rY=45,pX=0,pY=0,is=false;
        let autoRot = setInterval(() => { if(!is){ rY += 0.4; cb.style.transform=`rotateX(${rX}deg) rotateY(${rY}deg)`; } }, 30);
        function start(e){is=true;clearInterval(autoRot);pX=e.touches?e.touches[0].clientX:e.clientX;pY=e.touches?e.touches[0].clientY:e.clientY}
        function move(e){if(!is)return;const x=e.touches?e.touches[0].clientX:e.clientX,y=e.touches?e.touches[0].clientY:e.clientY,dX=x-pX,dY=y-pY;rY+=dX*0.4;rX-=dY*0.4;rX=Math.max(-80,Math.min(80,rX));cb.style.transform=`rotateX(${rX}deg) rotateY(${rY}deg)`;pX=x;pY=y}
        function end(){is=false}
        window.addEventListener('mousedown',start);window.addEventListener('mousemove',move);window.addEventListener('mouseup',end);
        window.addEventListener('touchstart',start,{passive:true});window.addEventListener('touchmove',move,{passive:true});window.addEventListener('touchend',end);

        // --- REPRODUCTOR ---
        const au=document.getElementById('au'),pb=document.getElementById('pb'),vi=document.getElementById('vi'),vA=document.getElementById('vA'),bA=document.getElementById('bA'),pG=document.getElementById('pG'),ct=document.getElementById('ct'),du=document.getElementById('du');
        function fmt(s){const m=Math.floor(s/60),r=Math.floor(s%60);return `${m}:${r<10?'0':''}${r}`}
        au.addEventListener('loadedmetadata',()=>{du.textContent=fmt(au.duration)});
        pb.addEventListener('click',()=>{if(au.paused){au.play();pb.textContent='║';pb.classList.add('pg');vi.classList.add('sp');vA.classList.add('pg')}else{au.pause();pb.textContent='▶';pb.classList.remove('pg');vi.classList.remove('sp');vA.classList.remove('pg')}});
        au.addEventListener('timeupdate',()=>{const pr=(au.currentTime/au.duration)*100;bA.style.width=pr+'%';ct.textContent=fmt(au.currentTime)});
        pG.addEventListener('click',(e)=>{const r=pG.getBoundingClientRect(),p=(e.clientX-r.left)/r.width;au.currentTime=p*au.duration});
    </script>
</body>
</html>
