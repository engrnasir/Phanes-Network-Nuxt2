<template>
    <div id="phanesNetwork" class="row">
      <h2 class="heading">Phanes Ecosystem</h2>
      <div class="cards">
          <div class="card" v-for="(card, index) in cards" :key="index">
              <img :src="require(`@/assets/${card.img}`)" alt="" class="icon">
              <h3 class="title">{{card.title}}</h3>
              <p class="snippet" @click="card.showAll = !card.showAll">
                  {{card.snippet.substring(0,125)}}<span v-if="card.showAll">{{card.snippet.substring(125)}}</span>
                  <span v-if="card.showAll===false && card.snippet.length>125" class="showMore">...</span>
                  
              </p>
          </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
      data(){
          return{
              cards:[
                  { img:'bag.png', title:'Phanes Index Portfolio', snippet:'The first utility of Phanes Network is the Phanes Index Portfolio (PIP).  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut, soluta ipsum ducimus nobis impedit minima dignissimos neque laborum commodi alias assumenda esse deserunt, culpa sint reprehenderit recusandae. Eum eius nam alias quisquam debitis. Odit voluptatibus corrupti in quisquam nam saepe eligendi perspiciatis unde minima labore voluptatum praesentium provident ipsam hic quidem dolorum consequuntur ea, ex delectus placeat doloremque mollitia sit! Quaerat doloremque ipsam, culpa nostrum rem, sapiente nemo quod totam quibusdam ea saepe error, inventore facere voluptates repellendus amet rerum ipsum excepturi nisi! Eos non quibusdam laborum est tempore ducimus eaque eligendi voluptates quam, ad quo repellat distinctio iure aliquid.',showAll:false},
                  { img:'cloud_db.png', title:'FAAS & SAAS', snippet:'Using our Farming-As-A-Service feature, users can use our well designed UI to provide staking and farming options and Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut, soluta ipsum ducimus nobis impedit minima dignissimos neque laborum commodi alias assumenda esse deserunt, culpa sint reprehenderit recusandae. Eum eius nam alias quisquam debitis. Odit voluptatibus corrupti in quisquam nam saepe eligendi perspiciatis unde minima labore voluptatum praesentium provident ipsam hic quidem dolorum consequuntur ea, ex delectus placeat doloremque mollitia sit! Quaerat doloremque ipsam, culpa nostrum rem, sapiente nemo quod totam quibusdam ea saepe error, inventore facere voluptates repellendus amet rerum ipsum excepturi nisi! Eos non quibusdam laborum est tempore ducimus eaque eligendi voluptates quam, ad quo repellat distinctio iure aliquid.',showAll:false},
                  { img: 'locker.png', title:'Liquidity Lockers', snippet:"Our liquidity lockers enable developers or liquidity providers to store LP tokens in a smart contract for their own desired period thereby revoking the locker's permission from removing the LP tokens from a start date to the due date. This helps prevent rug pulls brought about by withdrawing liquidity and helps projects gain trust.",showAll:false},
                  { img:'vesting.png', title:'Token Vesting', snippet:'Similar to Liquidity locking, our token vesting enables projects to lock tokens and set various unlock dates for the tokens. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut, soluta ipsum ducimus nobis impedit minima dignissimos neque laborum commodi alias assumenda esse deserunt, culpa sint reprehenderit recusandae. Eum eius nam alias quisquam debitis. Odit voluptatibus corrupti in quisquam nam saepe eligendi perspiciatis unde minima labore voluptatum praesentium provident ipsam hic quidem dolorum consequuntur ea, ex delectus placeat doloremque mollitia sit! Quaerat doloremque ipsam, culpa nostrum rem, sapiente nemo quod totam quibusdam ea saepe error, inventore facere voluptates repellendus amet rerum ipsum excepturi nisi! Eos non quibusdam laborum est tempore ducimus eaque eligendi voluptates quam, ad quo repellat distinctio iure aliquid.',showAll:false},
                  { img:'minting.png', title:'Token Minting', snippet:'With no coding required, users can use this feature to create their own fully ERC-20 compliant token in a few minutes. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut, soluta ipsum ducimus nobis impedit minima dignissimos neque laborum commodi alias assumenda esse deserunt, culpa sint reprehenderit recusandae. Eum eius nam alias quisquam debitis. Odit voluptatibus corrupti in quisquam nam saepe eligendi perspiciatis unde minima labore voluptatum praesentium provident ipsam hic quidem dolorum consequuntur ea, ex delectus placeat doloremque mollitia sit! Quaerat doloremque ipsam, culpa nostrum rem, sapiente nemo quod totam quibusdam ea saepe error, inventore facere voluptates repellendus amet rerum ipsum excepturi nisi! Eos non quibusdam laborum est tempore ducimus eaque eligendi voluptates quam, ad quo repellat distinctio iure aliquid.',showAll:false},
                  { img:'ilo_plateform.png', title:'ILO platform', snippet:'Initial Liquidity Offering is a decentralised launchpad for projects seeking to raise funds or liquidity for their projects without Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut, soluta ipsum ducimus nobis impedit minima dignissimos neque laborum commodi alias assumenda esse deserunt, culpa sint reprehenderit recusandae. Eum eius nam alias quisquam debitis. Odit voluptatibus corrupti in quisquam nam saepe eligendi perspiciatis unde minima labore voluptatum praesentium provident ipsam hic quidem dolorum consequuntur ea, ex delectus placeat doloremque mollitia sit! Quaerat doloremque ipsam, culpa nostrum rem, sapiente nemo quod totam quibusdam ea saepe error, inventore facere voluptates repellendus amet rerum ipsum excepturi nisi! Eos non quibusdam laborum est tempore ducimus eaque eligendi voluptates quam, ad quo repellat distinctio iure aliquid.',showAll:false},
              ]
          }
      },
      methods:{
          getSnippet(card){
              card.showAll = !card.showAll
              console.log(card);
              if(card.snippet.length > 125 && card.showAll){
                  return card.snippet.substring(0,125)+'...'
              }
              return card.snippet
  
          }
      }
     
  }
  </script>
  
  <style lang="scss" scoped>
      #phanesNetwork{
          padding-top: 50px;
          padding: 50px 24px 230px 24px;
          .heading{
              font-size: 48px;
              line-height: 59px;
              margin-bottom: 50px;
              @media  only screen and (min-width:1500px) {
                  margin-left: 24px;                
              }
              @media  only screen and (max-width:780px) {
                  text-align: center;             
              }
  
          }
          .cards{
              width: 100%;
              display: grid;
              grid-template-columns: repeat(3,1fr);
              gap: 27px;
              justify-content: space-between;
              justify-items: center;
              @media only screen and (max-width:1410px){
                  grid-template-columns: repeat(2,1fr);
              }
              @media only screen and (max-width:780px){
                  grid-template-columns: repeat(1,1fr);
              }
              .card{
                  width: 443px;
                  min-height: 284px;
                  height: min-content;
                  padding: 30px;
                  background: #010D09;
                  color: #E1E1E1;
  
                  position: relative;
                  $border: 3px;
                  background-clip: padding-box; /* !important?? */
                  border: solid $border transparent; /* !important?? */
                  border-radius: 1em;
                  transition: all .25s;
                  @media only screen and (max-width:1410px){
                      width: 100%;
                      min-width: 340px;
                  }
                  @media only screen and (max-width:980px){
                      min-height: 315px;
                  }
                  @media only screen and (max-width:580px){
                      min-width: 320px;
                  }
  
  
                  &:before {
                      content: '';
                      position: absolute;
                      top: 0; right: 0; bottom: 0; left: 0;
                      z-index: -1;
                      margin: -$border; /* !important?? */
                      border-radius: inherit; /* !important?? */
                      background: linear-gradient(135deg, #010D09, #1BD19C, #010D09);
                  }
                 
    
                  .icon{
                      width: 70px;
                      height: 70px;
                      margin-bottom: 14px;
                  }
                  .title{
                      font-weight: 800;
                      font-size: 24px;
                      line-height: 29px;
                      margin-bottom: 14px;
                  }
                  .snippet{
                      font-weight: 500;
                      font-size: 17px;
                      line-height: 29px;                    
                  }
              }
              .card:hover,
              .active{
                  border: none;
                  border-radius: 15px;
                  background: #1BD19C;
                  color: #010D09;
                  cursor: pointer;
                  &::before{
                      margin: 0;
                  }
              }
          }
      }
  
  
  
  
  
      
  </style>
  
  
  