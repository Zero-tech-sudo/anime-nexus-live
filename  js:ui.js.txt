const posters=[
{img:"https://image.tmdb.org/t/p/w500/qJ2tW6WMUDux911r6m7haRef0WH.jpg",title:"Cyber Re:Born",ep:"Ep 12"},
{img:"https://image.tmdb.org/t/p/w500/9ggJ2xHtUvwGaHv8xo9kUI9pD3I.jpg",title:"Neon Eclipse",ep:"Ep 8"},
{img:"https://image.tmdb.org/t/p/w500/gt4ia6IgaLlrmKkTkr8e5L2gKZF.jpg",title:"Ghost in the Shell: SAC_2045",ep:"Ep 24"},
{img:"https://image.tmdb.org/t/p/w500/sgBlyxjwpRDXJqgvH5buBVGpXqZ.jpg",title:"Akira Remastered",ep:"Movie"},
{img:"https://image.tmdb.org/t/p/w500/h5pAEVmaJRUF8vKEObT6gz8kR8k.jpg",title:"Steins;Gate 0",ep:"Ep 23"},
{img:"https://image.tmdb.org/t/p/w500/6KvpEo4Eg4X2f6MNkW6aR2IBYVL.jpg",title:"Chainsaw Man",ep:"Ep 12"}
];
function card(an,classic=false){
  const div=document.createElement('div');div.className='shelf-item';
  if(classic) div.classList.add('retro');
  div.innerHTML=`<img src="${an.img}" alt="${an.title}"><div class="shelf-meta"><div class="title">${an.title}</div><div class="ep">${an.ep}</div></div>`;
  return div;
}
['trending','new','classics'].forEach(k=>{
  const track=document.querySelector(`[data-shelf=${k}] .shelf-track`);
  posters.forEach(p=>{
    const c=card(p,k==='classics'); if(k==='new'){const pill=document.createElement('span');pill.className='new-pill';pill.textContent='NEW';c.append(pill);}
    track.append(c);
  });
});
