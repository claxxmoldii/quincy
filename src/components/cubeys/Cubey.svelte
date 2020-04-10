<style type="text/css">
  .isCubey {
    display: grid;
    background-color: whitesmoke;
    place-items: center center;
    text-align: center;
    height: 40vh;
    position: relative;
  }

  .isCubey:hover {
    cursor: pointer;
  }

  .isCubey h4 {
    font-size: 1.8rem;
    font-weight: 400;
    color: indianred;
    border-bottom: solid 1px crimson;
    display: inline-block;
    padding: 20px 0;
  }

  .isCubey p {
    color: hsla(0, 0%, 50%, 1);
    font-weight: 300;
    width: 200px;
  }

  .isCubey:hover h4 {
    animation: down .5s 1;
    animation-fill-mode: forwards;
  }

  .isCubey:not( :hover ) h4 {
    animation: up .5s 1;
    animation-fill-mode: forwards;
  }

  .isCubey:hover .frenchie {
    animation: out .5s 1;
    animation-fill-mode: forwards;
  }

  .isCubey:not( :hover ) .frenchie{
    animation: in .5s 1;
    animation-fill-mode: forwards;
  }

  .isCubey:hover .isLink {
    animation-delay: .5s;
    animation: in .5s 1;
    animation-fill-mode: forwards;
  }

  .isLink {
    font-size: 3rem;
    opacity: 0;
    position: absolute;
    bottom: 50px;
  }

  @keyframes out {
    0% { opacity: 1; }
    100% { opacity: 0; }
  }

  @keyframes in {
    0% { opacity: 0; }
    100% { opacity: 1; }
  }

  @keyframes down {
    0% { transform: translateY(0); }
    100% { transform: translateY(20px); }
  }

  @keyframes up {
    0% { transform: translateY(20px); }
    100% { transform: translateY(0px); }
  }
</style>

<div class="isCubey">
    <h4><slot name="isTitle"></slot></h4>
    <p class="frenchie"><slot name="isFrenchie"></slot></p>
    <p class="isLink"> + </p>
</div>
