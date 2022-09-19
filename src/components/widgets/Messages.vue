<template>
  <!-- @TODO: 
          may need to add overrides
  -->
  <WidgetContainer title="Messages">
    <div class="chat">
      <TabView>
        <TabPanel>
          <template #header>
            <img
              src="/assets/demo/images/avatar/asiyajavayant.png"
              alt="user"
            />
            <span class="p-badge">3</span>
          </template>
          <div class="chat">
            <span class="fade"></span>
            <div class="chat-content overflow-hidden py-0 pl-4 pr-3">
              <ScrollPanel class="w-full" style="height: 266px">
                <div class="chat-message send">
                  <span class="name">You</span>
                  <div class="message">
                    <p>
                      Hello Amy, I'd like to go over your latest course review.
                    </p>
                    <span>3 mins ago</span>
                  </div>
                  <div class="message">
                    <p>whenever you are available</p>
                    <span>3 mins ago</span>
                  </div>
                </div>
                <div class="chat-message">
                  <span class="name">Amy Fauser</span>
                  <div class="message">
                    <p>Ok, no problem. Are you available after class?</p>
                    <span>3 mins ago</span>
                  </div>
                </div>
                <div class="chat-message send">
                  <span class="name">You</span>
                  <div class="message">
                    <p>Yes, that would be fine</p>
                    <span>3 mins ago</span>
                  </div>
                </div>
                <div class="chat-message">
                  <span class="name">Amy Fauser</span>
                  <div class="message">
                    <p>Ok, we will meet then. Thank you</p>
                    <span>3 mins ago</span>
                  </div>
                </div>
                <div class="chat-message send">
                  <span class="name">You</span>
                  <div class="message">
                    <p>See you then</p>
                    <span>3 mins ago</span>
                  </div>
                </div>
                <div class="chat-message"></div>
              </ScrollPanel>
            </div>
            <div class="chat-input">
              <InputText type="text" placeholder="Write here..." />
            </div>
          </div>
        </TabPanel>
        <TabPanel>
          <template #header>
            <img
              src="/assets/demo/images/dashboard/avatar/af1.png"
              alt="user"
            />
            <span class="p-badge">1</span>
          </template>
          <div class="chat">
            <span class="fade"></span>
            <div class="chat-content">
              <div class="chat-message">
                <span class="name">Steven Smith</span>
                <div class="message">
                  <p>Hi Professor, I'm having trouble launching my course</p>
                  <span>3 mins ago</span>
                </div>
              </div>
              <div class="chat-message send">
                <span class="name">You</span>
                <div class="message">
                  <p>What trouble are you encountering?</p>
                  <span>3 mins ago</span>
                </div>
              </div>
              <div class="chat-message"></div>
            </div>
            <div class="chat-input">
              <InputText type="text" placeholder="Write here..." />
            </div>
          </div>
        </TabPanel>
        <TabPanel>
          <template #header>
            <img
              src="/assets/demo/images/dashboard/avatar/wm9.png"
              alt="user"
            />
          </template>
          <div class="chat">
            <div class="chat-content no-message">
              <h4>No Message From Theo Jefferson</h4>
            </div>
            <div class="chat-input">
              <input pInputText type="text" placeholder="Write here..." />
            </div>
          </div>
        </TabPanel>
        <!-- <TabPanel>
                <template #header>
                    <img src="/assets/demo/images/dashboard/avatar/wm6.png" alt="user" />
                </template>
                <div class="chat">
                    <div class="chat-content no-message">
                        <h4>No Message From Pat Samson</h4>
                    </div>
                    <div class="chat-input">
                        <input pInputText type="text" placeholder="Write here..." />
                    </div>
                </div>
            </TabPanel> -->
        <TabPanel>
          <template #header>
            <i class="pi pi-plus"></i>
          </template>
          <div class="chat">
            <span class="fade"></span>
            <div class="contacts">
              <ul>
                <li>
                  <img
                    src="/assets/demo/images/dashboard/avatar/avatar-6.png"
                    alt="user"
                  />
                  <div class="contact-info">
                    <h6>Vicky Molina</h6>
                    <span>Active</span>
                  </div>
                </li>
                <li>
                  <img
                    src="/assets/demo/images/dashboard/avatar/wm2.png"
                    alt="user"
                  />
                  <div class="contact-info">
                    <h6>James Ramos</h6>
                    <span>Active</span>
                  </div>
                </li>
                <li>
                  <img
                    src="/assets/demo/images/dashboard/avatar/wm5.jpg"
                    alt="user"
                  />
                  <div class="contact-info">
                    <h6>Aaron Tanner</h6>
                    <span>Active</span>
                  </div>
                </li>
                <li>
                  <img
                    src="/assets/demo/images/dashboard/avatar/wf2.png"
                    alt="user"
                  />
                  <div class="contact-info">
                    <h6>Rachel King</h6>
                    <span>Active</span>
                  </div>
                </li>
                <li>
                  <img
                    src="/assets/demo/images/dashboard/avatar/wf4.jpg"
                    alt="user"
                  />
                  <div class="contact-info">
                    <h6>Michelle Gilbert</h6>
                    <span>Active</span>
                  </div>
                </li>
                <li>
                  <img
                    src="/assets/demo/images/dashboard/avatar/wf3.jpg"
                    alt="user"
                  />
                  <div class="contact-info">
                    <h6>Linda Holt</h6>
                    <span>Active</span>
                  </div>
                </li>
              </ul>
            </div>
            <div class="chat-input">
              <InputText type="text" placeholder="Search new person" />
            </div>
          </div>
        </TabPanel>
      </TabView>
    </div>
  </WidgetContainer>
</template>

<script>
import WidgetContainer from '../WidgetContainer.vue';

export default {
  components: {
    WidgetContainer,
  },
};
</script>

<style lang="scss" scoped>
.chat {
  .p-tabview {
    .p-tabview-nav {
      background-color: transparent;
      margin: 0 -10px;
      border: none;
      &:before {
        display: none;
      }
      li {
        padding: 9px 0 0;
        display: -ms-flexbox;
        display: flex;
        -ms-flex-align: center;
        align-items: center;
        -ms-flex-pack: center;
        justify-content: center;
        background-color: transparent;
        -moz-transition: all 0.2s;
        -o-transition: all 0.2s;
        -webkit-transition: all 0.2s;
        transition: all 0.2s;
        margin: 0 10px;
        border: none;
        a {
          position: relative;
          width: 52px;
          height: 52px;
          -moz-border-radius: 20px;
          -webkit-border-radius: 20px;
          border-radius: 20px;
          display: -ms-flexbox;
          display: flex;
          -ms-flex-align: center;
          align-items: center;
          -ms-flex-pack: center;
          justify-content: center;
          background-color: #d0d6dd;
          cursor: pointer;
          -moz-transition: all 0.2s;
          -o-transition: all 0.2s;
          -webkit-transition: all 0.2s;
          transition: all 0.2s;
          color: #387fe9;
          color: var(--primary-color);
          border: 0 none;
          overflow: visible;
          img {
            -moz-border-radius: 20px;
            -webkit-border-radius: 20px;
            border-radius: 20px;
          }
          .p-badge {
            position: absolute;
            bottom: -5px;
            right: -5px;
          }
        }
        &.p-highlight {
          padding: 0 0 9px;
          border: none;
          a {
            box-shadow: 0px 0px 1px rgba(41, 50, 65, 0.16),
              0px 1px 2px rgba(41, 50, 65, 0.04),
              0px 6px 12px rgba(41, 50, 65, 0.24);
            border: 0 none;
            &:before {
              content: '';
              width: 12px;
              height: 2px;
              background: #387fe9;
              background: var(--primary-color);
              border-radius: 3px;
              position: absolute;
              bottom: -10px;
            }
          }
        }
        &:hover {
          border: none;
          padding: 0 0 9px;
        }
      }
    }
    .p-tabview-panels {
      background-color: transparent;
      border: none;
      padding: 16px 0 0;
      .p-tabview-panel {
        padding: 0;
        height: 350px;
        .chat {
          position: relative;
          display: -ms-flexbox;
          display: flex;
          -ms-flex-direction: column;
          flex-direction: column;
          -ms-flex-pack: justify;
          justify-content: space-between;
          height: 350px;
          .fade {
            position: absolute;
            top: 0;
            left: 0;
            display: block;
            width: 100%;
            height: 44px;
            background-image: linear-gradient(
              180deg,
              #293241 0%,
              rgba(234, 237, 243, 0) 100%
            );
          }
          .chat-content {
            max-height: 400px;
            overflow: auto;
            padding: 30px 6px 12px;
            flex: 1 1 auto;
            .chat-message {
              display: -ms-flexbox;
              display: flex;
              flex-direction: column;
              .name {
                display: block;
                color: #bfc2c6;
                font-weight: 600;
                font-size: 10px;
                line-height: 14px;
                margin: 0.25rem;
                &:first-of-type {
                  margin-top: 0;
                }
              }
              .message {
                max-width: 250px;
                padding: 8px 10px;
                box-shadow: 0px 0px 1px rgba(41, 50, 65, 0.5),
                  0px 1px 1px rgba(41, 50, 65, 0.2);
                -moz-border-radius: 12px;
                -webkit-border-radius: 12px;
                border-radius: 12px;
                background-color: #303a48;
                margin-bottom: 8px;
                p {
                  padding: 0;
                  margin: 0 0 2px;
                  color: #eaebec;
                }
                span {
                  display: block;
                  font-weight: 600;
                  font-size: 10px;
                  line-height: 14px;
                  color: #bfc2c6;
                }
              }
              &.send {
                -ms-flex-align: end;
                align-items: flex-end;
                .message {
                  span {
                    text-align: right;
                  }
                }
              }
            }
            &.no-message {
              display: -ms-flexbox;
              display: flex;
              -ms-flex-align: center;
              align-items: center;
              -ms-flex-pack: center;
              justify-content: center;
              h4 {
                color: #bfc2c6;
              }
            }
          }
          .contacts {
            flex: 1 1 auto;
            max-height: 400px;
            overflow: auto;
            padding: 0px 0 12px;
            ul {
              padding: 0;
              margin: 0;
              list-style: none;
              > li {
                display: -ms-flexbox;
                display: flex;
                -ms-flex-align: center;
                align-items: center;
                margin-bottom: 6px;
                -moz-transition: all 0.2s;
                -o-transition: all 0.2s;
                -webkit-transition: all 0.2s;
                transition: all 0.2s;
                cursor: pointer;
                padding: 8px 10px;
                -moz-border-radius: 12px;
                -webkit-border-radius: 12px;
                border-radius: 12px;
                img {
                  margin-right: 12px;
                  -moz-border-radius: 20px;
                  -webkit-border-radius: 20px;
                  border-radius: 20px;
                }
                h6 {
                  margin: 0 0 2px;
                  color: #eaebec;
                }
                span {
                  display: block;
                  color: #bfc2c6;
                  font-weight: 600;
                  font-size: 10px;
                  line-height: 14px;
                }
                &:hover {
                  background-color: #303a48;
                }
              }
            }
          }
          .chat-input {
            margin-top: 30px;
            input {
              width: 100%;
              -moz-border-radius: 24px;
              -webkit-border-radius: 24px;
              border-radius: 24px;
              padding: 20px 19px;
              background-color: #3e4754;
              border: none;
            }
          }
        }
      }
    }
  }
}
</style>
