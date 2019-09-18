<!--
 * @Description: 彩色简历首页
 * @Author: oldestcrab
 * @Github:
 * @Date: 2019-09-18 13:59:58
 * @LastEditors: oldestcrab
 * @LastEditTime: 2019-09-18 14:02:02
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
      <div class="content__left">
        <!-- 自我介绍 -->
        <div class="section">
          <div class="section-headline">
            {{ lang.about }}
          </div>

          <div class="section-content section-content--plain">
            <br/>
            {{ person.about }}
            <br/>
            <br/>
            {{ person.knowledge }}
          </div>
        </div>
        <span><br/></span>
        <!-- 兴趣爱好 -->
        <div
          v-if="person.hobbies"
          class="section">
          <div class="section-headline">
            {{ lang.hobbies }}
          </div>

          <div class="section-content-grid">
            <a
              v-for="(hobbies, index) in person.hobbies"
              class="grid-item"
              :key="index"
              :href="hobbies.url">
              <span class="squarred-grid-item">
                {{ hobbies.name }}
              </span>
              <span><br/></span>
            </a>
          </div>
          <span><br/></span>

    <!-- 技能 -->
    <div class="section-headline">
      {{ lang.skills }}
    </div>
    <div class="section-content-grid">
      <a
        v-for="(skills, index) in person.skills"
        class="grid-item"
        :key="index"
        :href="skills.url">
        <span class="squarred-grid-item">
          {{ skills.name }}
        </span>
        <span><br/></span>
      </a>
    </div>
    <span><br/></span>
    <!-- 个人信息 -->
    <div class="section-headline">
      {{ lang.contact }}
    </div>
    <div class="item">
      <div class="icon">
        <i class="material-icons">account_circle</i>
      </div>
      <div class="text">
          {{ lang.born }} {{person.birth.year}} {{ lang.bornIn }} {{person.birth.location}}
      </div>
    </div>

    <div class="item">
      <div class="icon">
        <i class="material-icons">location_city</i>
      </div>
      <div class="text">
          {{person.contact.city}}，{{person.contact.street}}
      </div>
    </div>

    <a :href="contactLinks.phone">
      <div class="item">
        <div class="icon">
          <i class="material-icons">phone</i>
        </div>
        <div class="text">
          {{person.contact.phone}}
        </div>
      </div>
    </a>

    <a :href="contactLinks.email">
      <div class="item">
        <div class="icon">
          <i class="material-icons">email</i>
        </div>
        <div class="text">
          {{person.contact.email}}
        </div>
      </div>
    </a>

    <a v-if="person.contact.github" :href="contactLinks.github" target="_blank">
      <div class="item">
        <div class="icon">
          <i class="fa fa-github"></i>
        </div>
        <div class="text">
          <span>@{{person.contact.github}}</span>
          <span>github.com/{{person.contact.github}}</span>
        </div>
      </div>
    </a>

    <a v-if="person.contact.website" :href="person.contact.website" target="_blank">
      <div class="item">
        <div class="icon">
          <i class="material-icons">language</i>
        </div>
        <div class="text">
          <span>{{person.contact.website}}</span>
        </div>
      </div>
    </a>
        </div>

        <!-- <div class="section">
          <div class="section-headline">
            {{ lang.contact }}
          </div>

          <div class="section-content section-content--plain">
            <div class="section-link">
              <i class="section-link__icon material-icons">phone</i>{{ person.contact.phone }}
            </div>

            <a
              class="section-link"
              :href="contactLinks.email">
              <i class="section-link__icon material-icons">mail</i>{{ person.contact.email }}
            </a>

            <div class="section-link">
              <i class="section-link__icon material-icons">business</i>{{ person.contact.street }}
            </div>

            <a
              v-if="person.contact.website"
              class="section-link"
              :href="person.contact.website">
              <i class="section-link__icon fa fa-globe"></i>{{ person.contact.website }}
            </a>

            <a
              v-if="person.contact.linkedin"
              class="section-link"
              :href="contactLinks.linkedin">
              <i class="section-link__icon fa fa-linkedin"></i>{{ person.contact.linkedin }}
            </a>

            <a
              v-if="person.contact.github"
              class="section-link"
              :href="contactLinks.github">
              <i class="section-link__icon fa fa-github"></i>{{ person.contact.github }}
            </a>

            <a
              v-if="person.contact.medium"
              class="section-link"
              :href="contactLinks.medium">
              <i class="section-link__icon fa fa-medium"></i>{{ person.contact.medium }}
            </a>
          </div>
        </div> -->
      </div>

      <div class="content__right">
        <div class="section">
          <!-- 工作经历 -->
          <div class="section-headline">
            <i class="section-headline__icon material-icons">work</i>{{ lang.experience }}
          </div>

          <div class="block" >
            <div class="block-helper" v-for="experience in person.experience" :key="experience.company" >
            <h3 class="headline" >{{experience.position}} - {{experience.company}}</h3>
              <div class="subheadline">{{experience.timeperiod}}</div>
              <p class="info">
                <!-- {{experience.description}} -->
              </p>
            </div>
          </div>
          <!-- <div class="section-content">
            <a
              v-for="(experience, index) in person.experience"
              :key="index"
              class="section-content__item"
              :href="experience.website">

              <span class="section-content__header">{{ experience.position }}</span>
              <span class="section-content__subheader">
                {{ experience.company }}
                <span class="section-content__plain">{{ experience.location }}</span>
              </span>

              <div class="section-content__text">{{ experience.timeperiod }}</div>
              <span class="section-content__text--light">{{ experience.description }}</span>
            </a>
          </div> -->
        </div>

        <!-- 教育经历 -->
        <div class="section">
          <div class="section-headline">
            <i class="section-headline__icon material-icons">school</i>{{ lang.education }}
          </div>
          <div class="block" >
            <div class="block-helper" v-for="education in person.education" :key="education.degree">
            <h3 class="headline">{{education.degree}} {{education.description}}</h3>
            <div class="subheadline">{{education.timeperiod}}</div>
            <p class="info">
                <!-- {{education.description}} -->
              </p>
          </div>
          </div>
          <!-- <div class="section-headline">
            <i class="section-headline__icon material-icons">school</i>{{ lang.education }}
          </div>

          <div class="section-content">
            <a
              v-for="(education, index) in person.education"
              class="section-content__item"
              :key="index"
              :href="education.website">

              <span class="section-content__header"> {{ education.school }} </span>
              <span class="section-content__subheader">{{ education.degree }}</span>
              <span class="section-content__text"> {{ education.timeperiod }} </span>
              <span class="section-content__text--light"> {{ education.description }} </span>
            </a>
          </div> -->
        </div>

        <!-- 专业技能 -->
        <div
          v-if="person.professional"
          class="section">
          <div class="section-headline">
            <i class="section-headline__icon material-icons">code</i>{{ lang.professional }}
          </div>
          <div class="block" >
            <div class="block-helper" v-for="professional in person.professional" :key="professional.name">
            <h3 class="headline">{{professional.name}}</h3>
            <!-- <p class="info">
              {{skill.level}}
            </p> -->
          </div>
          </div>
          <!-- <div class="section-content-grid">
            <a v-for="(project, index) in person.projects" :key="index"
              class="section-content__item-grid"
              :href="project.url">
              <span class="section-content__header"> {{ project.name }} </span>
              <span class="section-content__subheader">{{ project.platform }}</span>
              <span class="section-content__text"> {{ project.description }} </span>
            </a>
          </div> -->
        </div>


        <!-- 贡献 -->
        <!-- <div
          v-if="person.contributions"
          class="section">
          <div class="section-headline">
            <i class="section-headline__icon fa fa-heart"></i>{{lang.contributions}}
          </div>

          <div class="section-content-grid">
            <a
              v-for="(contribution, index) in person.contributions"
              class="section-content__item-grid"
              :key="index"
              :href="contribution.url">
              <span class="section-content__header"> {{ contribution.name }} </span>
              <span class="section-content__text"> {{ contribution.description }} </span>
              <span class="section-content__text--light" style="word-break: break-all;">
                {{ contribution.url }}
              </span>
            </a>
          </div>
        </div> -->
      </div>
    </div>

    <img class="picture"/>
  </div>
</template>

<script>
import Vue from 'vue';
import { getVueOptions } from './options';

const name = 'color_1';

export default Vue.component(name, getVueOptions(name));
</script>

<style lang="less" scoped>
@accent-color: #34495E;
@banner-color: #42b883;
@banner-height: 120px;
@picture-size: 120px;
@picture-offset: 35px;
@base-padding: 30px;
@left-column-width: 240px;

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
  border: 3px solid @accent-color;
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
  color: white;

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
    // margin-top:5px;
    // margin-bottom:5px;
    display:inline-block;
    box-shadow:0 2px 5px 0 rgba(0,0,0,0.16), 0 2px 10px 0 rgba(0,0,0,0.12);
    .headline {
      font-weight:300;
      // display:block;
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
      color: white;
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
    color: white;
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
  border: 1px solid white;
  color: white;
  margin-top: 5px;
  padding: 5px;
}
</style>
