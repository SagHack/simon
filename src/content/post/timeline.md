---
title: Como hacer un timeline en html
description: 'HTML para un timeline'
publishDate: 28 March 2024
tags: []
draft: true
---
## Para usar el timeline
<style>
{
  box-sizing: border-box;
}

/* The actual timeline (the vertical ruler) */
.timeline {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
}

/* The actual timeline (the vertical ruler) */
.timeline::after {
  content: '';
  position: absolute;
  width: 6px;
  background-color: gray;
  top: 0;
  bottom: 0;
  left: 50%;
  margin-left: 0px;
}

/* Container around content */
.container {
  padding: 10px 40px;
  position: relative;
  background-color: inherit;
  width: 50%;
}

/* The circles on the timeline */
.container::after {
  content: '';
  position: absolute;
  width: 25px;
  height: 25px;
  right: -17px;
  background-color: white;
  border: 4px solid #FF9F55;
  top: 15px;
  border-radius: 60%;
  z-index: 1;
}

/* Place the container to the left */
.left {
  left: 0;
}

/* Place the container to the right */
.right {
  left: 51%;
}

/* Add arrows to the left container (pointing right) */
.left::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  right: 30px;
  border: medium solid #FF9F55; /* Añadir un borde sólido de tamaño medio con el mismo color naranja (#FF9F55) */
  border-width: 10px 0 10px 10px;
  border-color: transparent transparent transparent #FF9F55; /* Asegurarse de que el color del borde sea el mismo que el del contenedor */
}

/* Add arrows to the right container (pointing left) */
.right::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  left: 30px;
  border: medium solid #FF9F55; /* Añadir un borde sólido de tamaño medio con el mismo color naranja (#FF9F55) */
  border-width: 10px 10px 10px 0;
  border-color: transparent #FF9F55 transparent transparent; /* Asegurarse de que el color del borde sea el mismo que el del contenedor */
}

/* Fix the circle for containers on the right side */
.right::after {
  left: -16px;
}

/* The actual content */
.content {
  padding: 0px 30px;
  background-color: inherit;
  position: relative;
  border-radius: 6px;
  border: 2px solid #FF9F55;
}

/* Media queries - Responsive timeline on screens less than 600px wide */
@media screen and (max-width: 600px) {
  /* Place the timelime to the left */
  .timeline::after {
  left: 31px;
  }
  
  /* Full-width containers */
  .container {
  width: 100%;
  padding-left: 70px;
  padding-right: 25px;
  }
  
  /* Make sure that all arrows are pointing leftwards */
  .container::before {
  left: 60px;
  border: medium solid white;
  border-width: 10px 10px 10px 0;
  border-color: transparent white transparent transparent;
  }

  /* Make sure all circles are at the same spot */
  .left::after, .right::after {
  left: 15px;
  }
  
  /* Make all right containers behave like the left ones */
  .right {
  left: 0%;
  }
}


</style>
<body>
<div class="timeline">
  <div class="container left">
    <div class="content">
      <h3>1948 - 10μm</h3>
      <p></p>
    </div>
  </div>
  <div class="container right">
    <div class="content">
      <h2>2016</h2>
      <p>Lorem ipsum dolor sit amet, quo ei simul congue exerci, ad nec admodum perfecto mnesarchum, vim ea mazim fierent detracto. Ea quis iuvaret expetendis his, te elit voluptua dignissim per, habeo iusto primis ea eam.</p>
    </div>
  </div>
  <div class="container left">
    <div class="content">
      <h2>2015</h2>
      <p>Lorem ipsum dolor sit amet, quo ei simul congue exerci, ad nec admodum perfecto mnesarchum, vim ea mazim fierent detracto. Ea quis iuvaret expetendis his, te elit voluptua dignissim per, habeo iusto primis ea eam.</p>
    </div>
  </div>
  <div class="container right">
    <div class="content">
      <h2>2012</h2>
      <p>Lorem ipsum dolor sit amet, quo ei simul congue exerci, ad nec admodum perfecto mnesarchum, vim ea mazim fierent detracto. Ea quis iuvaret expetendis his, te elit voluptua dignissim per, habeo iusto primis ea eam.</p>
    </div>
  </div>
  <div class="container left">
    <div class="content">
      <h2>2011</h2>
      <p>Lorem ipsum dolor sit amet, quo ei simul congue exerci, ad nec admodum perfecto mnesarchum, vim ea mazim fierent detracto. Ea quis iuvaret expetendis his, te elit voluptua dignissim per, habeo iusto primis ea eam.</p>
    </div>
  </div>
  <div class="container right">
    <div class="content">
      <h2>2007</h2>
      <p>Lorem ipsum dolor sit amet, quo ei simul congue exerci, ad nec admodum perfecto mnesarchum, vim ea mazim fierent detracto. Ea quis iuvaret expetendis his, te elit voluptua dignissim per, habeo iusto primis ea eam.</p>
    </div>
  </div>
</div>

</body>

