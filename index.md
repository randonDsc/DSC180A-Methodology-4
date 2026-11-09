Name: Po-Chen Lin

Email: p5lin@ucsd.edu

**1. What is the most interesting topic covered in your domain this quarter?**
I think the most interesting topic is residual reinforcement learning. Instead of building a model that has full control and replace PID controller, it is a lot cheaper and easier to combine the model with traditional method(at least what we expected). Using the traiditional PID controller as a baseline, the model is only responsible to conduct minor changes to stabilize the flying of the drone. Within this workflow, under wind speeds of 8–10 m/s, which exceeded the maximum wind speed of 7 m/s used during training, the average position RMSE decreased from 1.653 m with PID alone to 0.181 m with PID + SAC, an improvement of approximately 89%. Additionally, the failure rate dropped from 62% to 0% across 60 open-air test flights in a complicate warehouse environment. 

**2. Describe a potential investigation you would like to pursue for your Quarter 2 Project.**
One potential investigation I would like to pursue is whether we can use the llm to controll the drone. Given the sensors input such as IMU, downward sensors, and GPS, whether the llm can give the command to PID while our SAC model is still active. Due to latency issue, we will only let the llm makes higher level decisions such as choosing waypoints destinations. We are interested whether the llms can conduct these tasks and if possible, to what degree we can shrink the model.

**3. What is a potential change you’d make to the approach taken in your current Quarter 1 Project?**
Although our model can generalize to the unseen wind condition, it is still larger than other successful model. For instance, within [Trajectory Tracking Controller for Quadrotor by Continual Reinforcement Learning in Wind-Disturbed Environment](https://www.mdpi.com/1424-8220/25/16/4895#Abstract_a1), they do end to end model, they only use 60,420 actor parameter while we have 100,872 actor parameter. Therefore, we should and will try their approach too and compare two results.

**4. What other techniques would you be interested in using in your project?**
I would like to try knowledge distillation. Other than previous paper mentions, there is another one with even use lesser parameters. They were able to compress the knowledge from 1,000 SAC teacher policies into a single model with only 2,084 parameters. Our current SAC actor has 100,872 parameters, so I would like to see whether we can use knowledge distillation to train a much smaller model while maintaining similar performance. [RAPTOR (2025)](https://arxiv.org/abs/2509.11481)