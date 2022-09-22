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
              src="/src/assets/img/avatars/girl1.png"
              alt="user"
            />
            <span class="p-badge">3</span>
          </template>
          <div class="chat">
            <span class="fade"></span>
            <div class="chat-content overflow-hidden pt-0 pl-4 pr-3">
              <ScrollPanel class="w-full" style="height: 300px">
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
              </ScrollPanel>
            </div>
            <div class="chat-input">
              <InputText class="gainsboro" type="text" placeholder="Write here..." />
            </div>
          </div>
        </TabPanel>
        <TabPanel>
          <template #header>
            <img
              src="/src/assets/img/avatars/guy1.png"
              alt="user"
            />
            <span class="p-badge">1</span>
          </template>
          <div class="chat">
            <span class="fade"></span>
            <div class="chat-content overflow-hidden py-0 pl-4 pr-3">
              <ScrollPanel class="w-full" style="height: 300px">
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
              src="/src/assets/img/avatars/girl2.png"
              alt="user"
            />
          </template>
          <div class="chat">
            <span class="fade"></span>
            <div class="chat-content no-message">
              <h4 class="rhythm text-base font-normal">No Message From Vicky Molina</h4>
            </div>
            <div class="chat-input">
              <InputText type="text" placeholder="Write here..." />
            </div>
          </div>
        </TabPanel>
        <TabPanel>
          <template #header>
            <i class="pi pi-plus"></i>
          </template>
          <div class="chat">
            <span class="fade"></span>
            <div class="contacts overflow-hidden pt-0 px-3">
              <ScrollPanel class="w-full" style="height: 300px">
                <ul>
                  <li>
                    <img
                      src="/src/assets/img/avatars/guy2.png"
                      alt="user"
                    />
                    <div class="contact-info">
                      <h6 class="text-base gainsboro">Theo Jefferson</h6>
                      <Chip label="Active" icon="pi pi-circle-fill text-xxs mr-1 lime-green" class="lime-green mr-1 text-xs mt-2" />
                    </div>
                  </li>
                  <li>
                    <img
                      src="/src/assets/img/avatars/guy3.png"
                      alt="user"
                    />
                    <div class="contact-info">
                      <h6 class="text-base gainsboro">James Ramos</h6>
                      <Chip label="Active" icon="pi pi-circle-fill text-xxs mr-1 lime-green" class="lime-green mr-1 text-xs mt-2" />
                    </div>
                  </li>
                  <li>
                    <img
                      src="/src/assets/img/avatars/guy4.png"
                      alt="user"
                    />
                    <div class="contact-info">
                      <h6 class="text-base gainsboro">Aaron Tanner</h6>
                      <Chip label="Active" icon="pi pi-circle-fill text-xxs mr-1 lime-green" class="lime-green mr-1 text-xs mt-2" />
                    </div>
                  </li>
                  <li>
                    <img
                      src="/src/assets/img/avatars/girl3.png"
                      alt="user"
                    />
                    <div class="contact-info">
                      <h6 class="text-base gainsboro">Rachel King</h6>
                      <Chip label="Active" icon="pi pi-circle-fill text-xxs mr-1 lime-green" class="lime-green mr-1 text-xs mt-2" />
                    </div>
                  </li>
                  <li>
                    <img
                      src="/src/assets/img/avatars/girl4.png"
                      alt="user"
                    />
                    <div class="contact-info">
                      <h6 class="text-base gainsboro">Michelle Gilbert</h6>
                      <Chip label="Active" icon="pi pi-circle-fill text-xxs mr-1 lime-green" class="lime-green mr-1 text-xs mt-2" />
                    </div>
                  </li>
                  <li>
                    <img
                      src="/src/assets/img/avatars/girl5.png"
                      alt="user"
                    />
                    <div class="contact-info">
                      <h6 class="text-base gainsboro">Linda Holt</h6>
                      <Chip label="Active" icon="pi pi-circle-fill text-xxs mr-1 lime-green" class="lime-green mr-1 text-xs mt-2" />
                    </div>
                  </li>
                </ul>
              </ScrollPanel>
            </div>
            <div class="chat-input">
              <InputText class="gainsboro" type="text" placeholder="Search new person" />
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
  .p-chip.lime-green {
    background: #2c402e;
  }
</style>
