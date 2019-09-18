<!--
 * @Description: 黑白简历第二页
 * @Author: oldestcrab
 * @Github:
 * @Date: 2019-05-07 20:45:25
 * @LastEditors: oldestcrab
 * @LastEditTime: 2019-09-18 14:11:15
 -->
<template>
  <div class="resume">
    <div class="banner">
      <div class="banner__fullname">{{ person.name.first }} {{ person.name.middle }} {{ person.name.last }}</div>
      <div class="banner__position">{{ person.position }}</div>
      <div id="info-flex">
                <div><span id="phone"><i class='fa fa-phone-square' aria-hidden="true"></i> {{person.contact.phone}}</span></div>
                <div><span id="email"><a :href='"mailto:" + person.contact.email'>
                  <i class="fa fa-envelope" aria-hidden="true"></i> {{person.contact.email}}</a></span></div>
                <!-- <span v-if="person.contact.website" id="website"><a :href='person.contact.website'><i class="fa fa-home" aria-hidden="true"></i> {{person.contact.website}}</a></span> -->
                <!-- <span v-if="person.contact.github" id="github"><a :href='contactLinks.github'><i class="fa fa-github" aria-hidden="true"></i> {{person.contact.github}}</a></span> -->
      </div>
      <!-- <div class="banner__location">{{ lang.born }} {{person.birth.year}} {{ lang.bornIn }} {{person.birth.location}}</div> -->
    </div>

    <div class="content">


      <div class="content__right">
        <div class="section">
          <!-- 工作经历 -->
          <div class="section-headline">
            <i class="section-headline__icon material-icons">work</i>{{ lang.experience }}
          </div>

          <div class="block" >
            <div class="block-helper"  >
            <h3 class="headline" >开发工程师 - 广州复能基因有限公司</h3>
              <div class="subheadline">since 2017.11</div>
              <p class="info">bmnars网站文章爬取项目
                <ul>
                  <li>
                    负责爬取与生物信息相关的各类资讯网站，院校、研究院等发布的生物相关文章，已爬取网站50+；
                  </li>
                  <li>
                    通过requests、selenium访问网站，使用re、xpath、PyQuery等抽取相关信息，清洗保存为xml文件，并存入mysql数据库；
                  </li>
                  <li>
                    爬取知网、维普等文献检索平台生物相关文章里面的关键词，并存入mysql数据库；
                  </li>
                </ul>
              </p>
              <p class="info">竞争对手分析项目
                <ul>
                  <li>
                    使用redis搭建并维护代理池、cookie池，代理、cookies等信息存入redis;
                  </li>
                  <li>
                    通过验证码识别、模拟登陆、使用代理池、cookie池等方法绕过网站反爬手段；
                  </li>
                  <li>
                    通过scrapy框架、多线程、代理池，使用re、xpath、PyQuery等抽取相关信息，快速爬取竞争对手网站基因蛋白等所有商品信息；
                  </li>
                </ul>
              </p>
              <p class="info">gene_disease项目
                <ul>
                  <li>
                    负责爬取各类生物数据库检索平台gene、disease相关信息；
                  </li>
                  <li>
                    通过scrapy框架等爬取与公司gene、disease产品相关的文章信息；
                  </li>
                  <li>
                    获取开源数据库中的gene、disease信息，整合为统一的数据库；
                  </li>
                </ul>
              </p>
            </div>
          </div>
          <div class="block" >
            <div class="block-helper"  >
            <h3 class="headline" >安全工程师 - 北京亿赛通科技发展有限责任公司</h3>
              <div class="subheadline">2017.06 - 2017.10</div>
              <p class="info">各类安全服务项目，根据不同项目需求，为客户提供漏洞扫描、配置核查、渗透测试等安全服务。
                <ul>
                  <li>
                    对移动多个系统使用RSAS、Nessuss进行漏洞扫描，并人工检查主机、数据库、防火墙等安全配置，撰写安全技术服务报告文档。
                  </li>
                  <li>
                    对联通信息服务业务系统使用RSAS、Nessuss进行漏洞扫描，基线核查以及渗透测试，对BSS系统进行安全渗透测试，撰写安全技术服务报告文档。
                  </li>
                  <li>
                    协助广东省测评中心，为省内多家事业单位提供漏洞扫描，基线核查以及渗透测试等安全服务，撰写安全技术服务报告文档。
                  </li>
                </ul>
              </p>
            </div>
          </div>
          <div class="block" >
            <div class="block-helper"  >
            <h3 class="headline" >运维实习生 - 广州天源迪科信息技术有限公司</h3>
              <div class="subheadline">2016.08 - 2017.03</div>
              <p class="info">联通OCS系统运维
                <ul>
                  <li>
                    负责联通OCS系统的日常Linux运维，及时解决出现的各种问题；
                  </li>
                  <li>
                    编写python脚本获取日志文件、备份文件等所需信息进行核查；
                  </li>
                  <li>
                    解决各级地市日常问题，核查mysql、Oracle等数据库相关数据
                  </li>
                </ul>
              </p>
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- <img class="picture"/> -->
  </div>
</template>

<script>
import Vue from 'vue';
import { getVueOptions } from './options';

const name = 'black_2';

export default Vue.component(name, getVueOptions(name));
</script>

<style lang="less" scoped>
@accent-color: #34495E;
@banner-color: white;
@banner-height: 120px;
@picture-size: 120px;
@picture-offset: 35px;
@base-padding: 30px;
@left-column-width: 180px;

a {
  color: inherit;
  cursor: pointer;
  text-decoration-line: none;

  &:visited {
    color: inherit;
  }
}

.resume {
  position: relative;
  font-family:'Roboto' !important;
  font-size: 0.9em;
}

.picture {
  position: absolute;
  top: @banner-height - @picture-offset;
  left: @left-column-width + @base-padding * 2 - @picture-size / 2;
  height: @picture-size;
  width: @picture-size;
  border-radius: 50%;
  border: 5px solid @accent-color;
  content: url('../../resume/id.jpg');
  z-index: 2;
}

.banner {
  width: calc(100% - @base-padding * 2);
  height: @banner-height;
  padding: @base-padding;
  background-color: @banner-color;
  /*
    background-image: url('../../resume/banner.png');
    background-repeat: no-repeat;
    background-size: cover;
  */
  color: black;

  &__fullname {
    font-size: 32px;
  }

  &__position {
    font-size: 16px;
  }

  &__location {
    font-size: 12px;
  }
  // 开头电话邮箱
  #info-flex {
                display:inline-block;
                margin-top:20px;
                font-size:14px;

                span {
                    margin-right:25px;
                }
                i {
                    margin-right:5px;
                }
            }
}

.content {
  display: flex;
  width: 100%;
  height: 100%;

  &__left,
  &__right {
    height: 100%;
    padding: @base-padding;
    .block {
    width:90%;
    position:relative;
    background-color:#ffffff;
    padding:20px;
    margin-top:20px;
    margin-bottom:20px;
    display:inline-block;
    box-shadow:0 2px 5px 0 rgba(0,0,0,0.16), 0 2px 10px 0 rgba(0,0,0,0.12);
    .headline {
      font-weight:300;
      display:block;
      font-size:15px;
      color:rgba(0,0,0,0.870588);
    }
    .subheadline {
      color:rgba(0,0,0,0.541176);
      display:block;
      font-size:14px;
      font-weight:300;
    }
    .info {
      font-size:14px;
      color:rgba(0,0,0,0.870588);
      margin-bottom:0;
      padding-top:2px;
    }
    .icon {
      width:16%;
      float:left;
      margin-left:0;
      .fa, .material-icons {
        text-align:center;
        display:block;
        font-size:30pt;
        color: black;
      }
    }
    .content {
      width:80%;
      position:absolute;
      height:96%;
      left:17%;
      padding-right:3%;
      text-align:left;
      display:flex;
      flex-direction:column;
      .item {
        border-bottom:1px solid #bdbdbd;
        flex:1;
        width:97%;
        display:flex;
        justify-content:center;
        flex-direction:column;
        text-align:left;
        padding-top:0;
        span {
          color:#d8ab94;
          margin-top:0;
          font-size:10pt;
          line-height:16pt;
        }
        p {
          margin-top:5px;
        }
      }
      .item:last-of-type {
        border-bottom-style:none;
        border-bottom-style:none;
      }
    }
  }
  }

  &__left {
    width: @left-column-width;
    color: rgba(255, 255, 255, 0.59);
    background-color: @accent-color;

    .section-headline {
      color: black;
    }
  .item {
    width:100%;
    margin-top:13px;
    float:left;
    .fa, .material-icons {
      display:inherit;
      text-align:left;
    }
    .icon {
      width:20%;
      float:left;
    }
    .text {
      float:right;
      width:69%;
      padding-right:10%;
      padding-top:1%;
      // display:inherit;
      font-size:15px;
      font-weight:300;

    }
    span {
      font-weight:300;
    }
  }
}

  &__right {
    flex: 1;
  }
}

.section {
  margin: 20px 0;
}

.section-link,
.section-headline {
  display: flex !important;
  align-items: center;
  color: @accent-color;
  display: inline-block;
  font-size: 1.2em;
  margin: 8px 0;

  &__icon {
    margin-right: 8px;
    font-size: 1.4em;
  }
}

.section-link {
  font-size: 1.1em;
  color: rgba(255, 255, 255, 0.59) !important;

  &__icon {
    color: black;
  }
}

.section-content {
  margin-top: 5px;
  padding-left: 32px;
  font-size: 14px;

  &__item {
    display: block;
    margin-bottom: 5px;
  }

  &__header {
    display: block;
    font-size: 1.1em;
    font-weight: 500;
  }

  &__subheader {
    display: block;
    font-weight: 400;
  }

  &__plain,
  &__text {
    display: block;
    font-size: 12px;

    &--light {
      font-size: 12px;
    }
  }

  &__plain {
    display: inline;
    font-weight: 300;
  }

  &__item-grid {
    flex: 1 1 0;
    margin-bottom: 5px;
    padding-right: 5px;
  }

  &--plain {
    padding: 0;
  }
}

.section-content-grid {
  display: flex;
  flex-wrap: wrap;
  margin-top: 5px;
  margin-bottom: 5px;
}

.grid-item {
  padding-right: 5px;
}

.squarred-grid-item {
  display: block;
  border: 1px solid black;
  color: black;
  margin-top: 5px;
  padding: 5px;
}
</style>
